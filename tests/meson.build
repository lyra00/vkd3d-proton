
vkd3d_test_flags = []
if vkd3d_platform == 'windows'
  if enable_standalone_d3d12
    vkd3d_test_deps = [ lib_d3d12, lib_dxgi ]
  else
    vkd3d_test_deps = [ vkd3d_dep, vkd3d_utils_dep ]
    vkd3d_test_flags = ['-DVKD3D_FORCE_UTILS_WRAPPER=1']
  endif
else
  vkd3d_test_deps = [ vkd3d_dep, vkd3d_utils_dep ]
endif

executable('d3d12', 'd3d12.c', vkd3d_headers,
  dependencies        : vkd3d_test_deps,
  include_directories : vkd3d_private_includes,
  install             : true,
  c_args              : vkd3d_test_flags,
  override_options    : [ 'c_std='+vkd3d_c_std ])

executable('descriptor-performance', 'descriptor_performance.c', vkd3d_headers,
  dependencies        : vkd3d_test_deps,
  include_directories : vkd3d_private_includes,
  install             : true,
  c_args              : vkd3d_test_flags,
  override_options    : [ 'c_std='+vkd3d_c_std ])
