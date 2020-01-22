cmake_minimum_required(VERSION 3.16)

project(Quake)

add_compile_definitions(
    USE_CODEC_WAVE
    USE_CODEC_MP3
	USE_CODEC_VORBIS
)

add_compile_options(
    -Wall
	-Wno-trigraphs
	-Werror=implicit
)

set(src
    Quake/strlcat.c
    Quake/strlcpy.c
    # GL
    Quake/gl_refrag.c
    Quake/gl_rlight.c
	Quake/gl_rmain.c
	Quake/gl_fog.c
	Quake/gl_rmisc.c
	Quake/r_part.c
	Quake/r_world.c
	Quake/gl_screen.c
	Quake/gl_sky.c
	Quake/gl_warp.c
	Quake/gl_vidsdl.c
	Quake/gl_draw.c
	Quake/gl_texmgr.c
	Quake/gl_mesh.c
	Quake/r_sprite.c
	Quake/r_alias.c
	Quake/r_brush.c
    Quake/gl_model.c
    # INPUT
    Quake/in_sdl.c
    # SND
    Quake/snd_dma.c
    Quake/snd_mix.c
    Quake/snd_mem.c
    Quake/bgmusic.c
    Quake/snd_codec.c
	Quake/snd_flac.c
	Quake/snd_wave.c
	Quake/snd_vorbis.c
	Quake/snd_opus.c
	Quake/snd_mp3.c
	Quake/snd_mp3tag.c
	Quake/snd_mikmod.c
	Quake/snd_xmp.c
    Quake/snd_umx.c
    Quake/snd_sdl.c
    # CDA
    Quake/cd_sdl.c
    # NET
    Quake/net_bsd.c
    Quake/net_udp.c
    Quake/net_dgrm.c
	Quake/net_loop.c
	Quake/net_main.c
    # OTHER
    Quake/chase.c
	Quake/cl_demo.c
	Quake/cl_input.c
	Quake/cl_main.c
	Quake/cl_parse.c
	Quake/cl_tent.c
	Quake/console.c
	Quake/keys.c
	Quake/menu.c
	Quake/sbar.c
	Quake/view.c
	Quake/wad.c
	Quake/cmd.c
	Quake/common.c
	Quake/crc.c
	Quake/cvar.c
	Quake/cfgfile.c
	Quake/host.c
	Quake/host_cmd.c
	Quake/mathlib.c
	Quake/pr_cmds.c
	Quake/pr_edict.c
	Quake/pr_exec.c
	Quake/sv_main.c
	Quake/sv_move.c
	Quake/sv_phys.c
	Quake/sv_user.c
	Quake/world.c
	Quake/zone.c
	Quake/image.c
	Quake/main_sdl.c
)

set(src
	${src}
	Quake/pl_linux.c
    Quake/sys_sdl_unix.c
)

add_executable(quake ${src})

target_link_libraries(quake
	m
    mad
    vorbisfile
    vorbis
    ogg
	SDL2
	OpenGL
	png
	GLEW
)
