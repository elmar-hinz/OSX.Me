
desc "Default task"
task :default do
     puts `rake -T`
end

desc "Backup"
task :backup do
    system 'ansible-playbook me.yml --tags="backup"'
end

desc "Dotfiles - nothing else"
task :dot do
    system 'ansible-playbook me.yml --tags="dotfiles"'
end

desc "Private role onyz"
task :private do
    system 'ansible-playbook me.yml --tags="private"'
end

desc "Quick run -  No backup, upgrades, superuser or dotfiles"
task :quick do
    system 'ansible-playbook me.yml --skip-tags="backup,upgrade,become,dotfiles"'
end

desc "Full run"
task :full do
    system 'ansible-playbook me.yml --ask-become-pass'
end


