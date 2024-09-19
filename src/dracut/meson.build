dracut = find_program('dracut', required: false)

if dracut.found()
  dracutmodule_dir = '/usr/lib/dracut/modules.d/60clevis-zfs'
  dracutmodule_data = configuration_data()
  dracutmodule_data.merge_from(data)
  dracutmodule_data.set('dracutmoduledir', dracutmodule_dir)
  configure_file(
    input: 'module-setup.sh.in',
    output: 'module-setup.sh',
    install_dir: dracutmodule_dir,
    configuration: dracutmodule_data,
  )
  configure_file(
    input: 'clevis-zfs-hook.sh.in',
    output: 'clevis-zfs-hook.sh',
    install_dir: dracutmodule_dir,
    configuration: dracutmodule_data,
  )
else
  warning('Will not install dracut module due to missing dependencies!')
endif


