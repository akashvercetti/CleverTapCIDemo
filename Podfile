# Uncomment the next line to define a global platform for your project
# platform :ios, '9.0'

target 'CleverTapCIDemo' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!

  # Pods for CleverTapCIDemo
  pod 'Leanplum-iOS-SDK'
end


target 'CleverTapCIDemoTests' do
  # Comment the next line if you don't want to use dynamic frameworks
  use_frameworks!

  # Pods for CleverTapCIDemo
  pod 'Leanplum-iOS-SDK'
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    if target.name == 'CleverTap-iOS-SDK'
        puts "Target CleverTap-iOS-SDK found."
        resource_files = target.resources_build_phase.files
        dummy = resource_files.find do |file|
            # puts "File: #{file.file_ref.name}"
            file.file_ref.name == 'AmazonRootCA1.cer'
        end
        resource_files.delete dummy
        puts "Deleting resource file #{dummy.inspect} from target #{target.inspect}."
    end
  end
end
