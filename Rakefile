task :default => :build

desc 'Jekyll build'
task :build do
  jekyll
#  compress
end

desc 'Jekyll --auto'
task :auto do
  jekyll('--auto')
end

desc 'Jekyll --server --auto'
task :server do
  jekyll('--server --auto')
end

desc 'Deploy to live'
task :live do
sh 'rsync -rtzhv --delete ../Website/ dhg:/home/sgeekup/sites/geekup.org/public/'
end

def jekyll(opts = '')
  sh 'rm -rf ../Website'
  sh 'jekyll ' + opts
end