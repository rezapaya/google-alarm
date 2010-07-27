# Google Alarm

task :default => :build

desc "Build add-on XPI"
task :build do
  sh "rm -f google-alarm.xpi"
  sh "zip google-alarm.xpi -r chrome chrome.manifest content install.rdf"
  sh "cp content/google-alarm.js google-alarm.user.js"
end

desc "Build & open the XPI w/ Firefox (Mac-oriented)"
task :install => :build do
  sh "open -a Firefox google-alarm.xpi"
end

desc "Build & deploy files to fffff.at"
task :deploy => :build do
  sh "rsync -rtzh --progress *.xpi *.js jamiew@jamiedubs.com:~/web/public/googlealarm/"
  sh "rsync -rtzh --progress website/* jamiew@jamiedubs.com:~/web/public/googlealarm/"
end
