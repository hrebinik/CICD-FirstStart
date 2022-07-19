# This file contains the fastlane.tools configuration
# You can find the documentation at https://docs.fastlane.tools
#
# For a list of all available actions, check out
#
#     https://docs.fastlane.tools/actions
#
# For a list of all available plugins, check out
#
#     https://docs.fastlane.tools/plugins/available-plugins
#

# Uncomment the line if you want fastlane to automatically update itself
# update_fastlane

default_platform(:ios)

platform :ios do
  desc "Does a static analysis of the project. Configure the options in .swiftlint.yml"
  lane :lint do
   swiftlint(
   mode: :lint,
   executable: "Pods/SwiftLint/swiftlint",
   reporter: "html",
   output_file: "fastlane/swiftlint-results.html",
   config_file: '.swiftlint.yml',
   ignore_exit_status: true
  )
end


  desc "Test an measure code coverage"
  lane :test do
   run_tests(devices: ["iPhone 13"])

   #xcov(
    #workspace: "iOSTemplate.xcworkspace",
    #scheme: "iOSTemplate",
    #output_directory: "fastlane/xcov_output",
    #json_report: true
   #)
end


def archive_project(scheme, filename)
        build_ios_app(
            workspace: "iOSTemplate.xcworkspace",
            configuration: scheme,
            scheme: scheme,
            silent: true,
            clean: true,
            output_directory: "./ipas",
            output_name: "#{filename}.ipa",
            export_method: "development",
            include_bitcode: false
        )
 end

def send_to_firebase(ipa_name, scheme)
    firebase_app_distribution(
        app:"1:813886581596:ios:0d49e76424fcf134d76f99",
        ipa_path: "./ipas/#{ipa_name}.ipa",
        firebase_cli_path: "/usr/local/bin/firebase"
    )
end


desc "Собрать проект с указанной схемой. Пример вызова: fastlane archive_project scheme:\"Dev\" filename:\"dev_1.2.3\""
lane :archive_project do |options|
    scheme = options[:scheme]
    filename = options[:filename]
    archive_project(scheme, filename)
end

desc "Собрать релизную сборку проекта. Пример вызова: fastlane archive_beta scheme:\"Prod\" filename:\"release_1.2.3\""
lane :archive_beta do |options|
    scheme = options[:scheme]
    filename = options[:filename]
    archive_project(scheme, filename)
end

desc "Отправить уже собранный архив ipa в фаербейз с указанным названием файла. Пример вызова: fastlane distribute_to_firebase 
filename:\"dev_1.2.3\" scheme:\"Dev\""
lane :distribute_to_firebase do |options|
    filename = options[:filename]
    scheme = options[:scheme]
    archive_project("iOSTemplate", "dev_0.0.1")
    send_to_firebase("dev_0.0.1", "iOSTemplate")
end


end
