task :default => :build

def windows?
  Gem.win_platform?
end

desc 'Jekyll build'
task :build do
  jekyll('build')
end

desc 'Jekyll serve with auto-reload'
task :auto do
  jekyll('serve')
end

desc 'Jekyll serve'
task :server do
  jekyll('serve')
end

desc 'Deploy to live, replaces live server with _site'
task :live do
  jekyll('build')
  sh 'rsync -rtzhv --delete _site/ dhg:/home/sgeekup/sites/geekup.org/public/'
end

def jekyll(opts = '')
  if windows?
    sh 'rmdir /s /q _site'
    sh 'mkdir _site'
  else
    sh 'rm -rf _site'
  end
  sh "bundle exec jekyll #{opts}"
end