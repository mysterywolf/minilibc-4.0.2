# RT-Thread building script for component

from building import *
Import('rtconfig')

cwd   = GetCurrentDir()
src     = Glob('*.c')
CPPPATH = [cwd]
group   = []

if rtconfig.PLATFORM == 'gcc' and GetDepend('RT_LIBC_USING_MINILIBC'):
    # https://gcc.gnu.org/onlinedocs/gcc-4.4.7/gcc/Link-Options.html
    CCFLAGS   = '-nostdinc'
    LINKFLAGS = ' -nostdlib'
    LIBS      = ['gcc']
    CPPDEFINES = ['RT_USING_MINILIBC']

    group = DefineGroup('minilibc', src, depend = [''], CPPPATH = CPPPATH, LINKFLAGS = LINKFLAGS, LIBS = LIBS, CPPDEFINES = CPPDEFINES)

Return('group')