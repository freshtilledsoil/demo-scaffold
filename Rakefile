desc 'Watch Sass/Bourbon files'
task :server do
  puts "Watching Sass files and including Bourbon"
  sassPid = Process.spawn('sass --watch css/sass:css -r ./css/sass/bourbon/lib/bourbon.rb')

  trap("INT") {
    [sassPid].each { |pid| Process.kill(9, pid) rescue Errno::ESRCH }
    exit 0
  }

  [sassPid].each { |pid| Process.wait(pid) }
end
