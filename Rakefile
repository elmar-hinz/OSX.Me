
desc "Default task"
task :default do
     puts `rake -T`
end

desc "Full run"
task :play do
    system 'ansible-playbook me.yml --ask-become-pass'
end

desc "Quick run -  No upgrades"
task :quick do
    system 'ansible-playbook me.yml --ask-become-pass --extra-vars="brew_upgrade=false"'
end

