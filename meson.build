project('satsmooth', ['c','cpp','cython'])

py_mod = import('python')
py3 = py_mod.find_installation('python3')

numpy_dep = dependency('numpy', version: '>=2.0.0',required: true)
omp = dependency('openmp')

py3.install_sources(
    [
     'src/satsmooth/__init__.py'
    ],
    subdir: 'satsmooth',
    pure: false
)


py3.install_sources(
    [
  'src/satsmooth/preprocessing/__init__.py',
  'src/satsmooth/preprocessing/fill_gaps_nb.py',
  'src/satsmooth/preprocessing/fill_gaps_py.py'
    ],
    subdir: 'satsmooth/preprocessing',
    pure: false
)


py3.install_sources(
    [
  'src/satsmooth/detect/__init__.py'
    ],
    subdir: 'satsmooth/detect',
    pure: false
)



py3.install_sources(
    [
  'src/satsmooth/anc/__init__.py',
  'src/satsmooth/anc/anc_smoothers.py'
    ],
    subdir: 'satsmooth/anc',
    pure: false
)


py3.install_sources(
    [
  'src/satsmooth/smooth/__init__.py',
    ],
    subdir: 'satsmooth/smooth',
    pure: false
)

py3.install_sources(
    [
    'src/satsmooth/utils/__init__.py',
    'src/satsmooth/utils/data_prep.py',
    'src/satsmooth/utils/tfill.py' 
    ],
    subdir: 'satsmooth/utils',
    pure: false
)


import('python').find_installation().extension_module(
  '_signal',
  'src/satsmooth/detect/_signal.pyx',
  dependencies : [numpy_dep, omp],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/detect',
  install : true
)

import('python').find_installation().extension_module(
  '_linear_interp',
  'src/satsmooth/preprocessing/_linear_interp.pyx',
  dependencies : [numpy_dep, omp],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/preprocessing',
  install : true
)

import('python').find_installation().extension_module(
  '_linear_interp_regrid',
  'src/satsmooth/preprocessing/_linear_interp_regrid.pyx',
  dependencies : [numpy_dep, omp],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/preprocessing',
  install : true
)

import('python').find_installation().extension_module(
  '_linear_interp_regrid_multi',
  'src/satsmooth/preprocessing/_linear_interp_regrid_multi.pyx',
  dependencies : [numpy_dep, omp],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/preprocessing',
  install : true
)

import('python').find_installation().extension_module(
  '_linear_interp_regrid_multi_indexing',
  'src/satsmooth/preprocessing/_linear_interp_regrid_multi_indexing.pyx',
  dependencies : [numpy_dep, omp],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/preprocessing',
  install : true
)

import('python').find_installation().extension_module(
  '_fill_gaps',
  'src/satsmooth/preprocessing/_fill_gaps.pyx',
  dependencies : [numpy_dep, omp],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/preprocessing',
  install : true
)

import('python').find_installation().extension_module(
  '_outlier_removal',
  'src/satsmooth/preprocessing/_outlier_removal.pyx',
  dependencies : [numpy_dep, omp],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/preprocessing',
  install : true
)

import('python').find_installation().extension_module(
  '_dl',
  'src/satsmooth/anc/_dl.pyx',
  dependencies : [numpy_dep, omp],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/anc',
  install : true
)


import('python').find_installation().extension_module(
  '_lowess_smooth',
  'src/satsmooth/anc/_lowess_smooth.pyx',
  dependencies : [numpy_dep, omp],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/anc',
  install : true
)


import('python').find_installation().extension_module(
  '_adaptive_bilateral',
  'src/satsmooth/smooth/_adaptive_bilateral.pyx',
  dependencies : [numpy_dep],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/smooth',
  install : true
)


import('python').find_installation().extension_module(
  '_rolling1d',
  'src/satsmooth/smooth/_rolling1d.pyx',
  dependencies : [numpy_dep],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/smooth',
  install : true
)


import('python').find_installation().extension_module(
  '_rolling2d',
  'src/satsmooth/smooth/_rolling2d.pyx',
  dependencies : [numpy_dep, omp],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/smooth',
  install : true
)

import('python').find_installation().extension_module(
  '_spatial_temporal',
  'src/satsmooth/smooth/_spatial_temporal.pyx',
  dependencies : [numpy_dep, omp],
  override_options: ['cython_language=cpp'],
  subdir: 'satsmooth/smooth',
  install : true
)
