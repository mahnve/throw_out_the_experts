BUILD_DIR='build'
BUILD_FILE= BUILD_DIR + '/testing_android_presentation.pdf'

task :default => :build

task :build do
  mkdir_p BUILD_DIR
  `svgslides -i list`
  mv 'slides.pdf', BUILD_FILE
end

task :view => :build do
  `evince #{BUILD_FILE}`
end

task :present => :build do
  IO.popen "evince -s #{BUILD_FILE}"
end

task :present_impressive => :build do
  IO.popen "impressive -t Crossfade #{BUILD_DIR}"
end
