package(default_visibility = ["//visibility:public"])

licenses(["notice"])  # BSD License

cc_library(
    name = "libmemcached",
    srcs = glob([
        "libhashkit-1.0/**/*.h",
        "libhashkit/**/*.cc",
        "libhashkit/**/*.h",
        "libhashkit/**/*.hpp",
        "libmemcached-1.0/**/*.h",
        "libmemcached/**/*.c",
        "libmemcached/**/*.cc",
        "libmemcached/**/*.h",
        "libmemcached/**/*.hpp",
        "libmemcachedprotocol-0.0/**/*.h",
        "util/*.cc",
        "util/*.hpp",
    ]),
    hdrs = [
        "config/libhashkit/hashkitcon.h",
        "config/mem_config.h",
    ],
    copts = [
        "-Wno-register",
        "-Wno-error",
    ],
    includes = [
        ".",
        "config",
    ],
    deps = [],
)

genrule(
    name = "hashkitcon_h",
    srcs = ["libhashkit/hashkitcon.h.in"],
    outs = ["config/libhashkit/hashkitcon.h"],
    cmd = ("sed " +
           "-e 's/@AUTOHEADER_FILE@/mem_config.h/g' " +
           "$< >$@"),
)

genrule(
    name = "mem_config_h",
    outs = ["config/mem_config.h"],
    cmd = "\n".join([
        "cat <<'EOF' >$@",
        "",
        "#pragma once",
        "#if defined( _SYS_FEATURE_TESTS_H) || defined(_FEATURES_H)",
        '#error "You should include mem_config.h as your first include file"',
        "#endif",
        "#define CINTTYPES_H <cinttypes>",
        "#define CSTDINT_H <cstdint>",
        "#define DEBUG 0",
        "#define DRIZZLED_BINARY 0",
        "#define GEARMAND_BINARY 0",
        "#define GEARMAND_BLOBSLAP_WORKER 0",
        "#define HAVE_ALARM 1",
        "#define HAVE_ALLOCA 1",
        "#define HAVE_ALLOCA_H 1",
        "#define HAVE_ARPA_INET_H 1",
        "#define HAVE_ATEXIT 1",
        "#define HAVE_CLOCK_GETTIME 1",
        "#define HAVE_DECL_STRERROR_R 1",
        "#define HAVE_DLFCN_H 1",
        "#define HAVE_DRIZZLED_BINARY 0",
        "#define HAVE_DUP2 1",
        "#define HAVE_ERRNO_H 1",
        "#define HAVE_EXECINFO_H 1",
        "#define HAVE_FCNTL 1",
        "#define HAVE_FCNTL_H 1",
        "#define HAVE_FEATURES_H 1",
        "#define HAVE_FNMATCH_H 1",
        "#define HAVE_FNV64_HASH 1",
        "#define HAVE_FORK 1",
        "#define HAVE_GCC_ABI_DEMANGLE 1",
        "#define HAVE_GCC_ATOMIC_BUILTINS 1",
        "#define HAVE_GEARMAND_BINARY 0",
        "#define HAVE_GETCWD 1",
        "#define HAVE_GETLINE 1",
        "#define HAVE_GETTIMEOFDAY 1",
        "#define HAVE_INET_NTOA 1",
        "#define HAVE_INTTYPES_H 1",
        "#define HAVE_IN_PORT_T 1",
        "#define HAVE_LIBCURL 0",
        "#define HAVE_LIBDRIZZLE 0",
        "#define HAVE_LIBEVENT 0",
        "#define HAVE_LIBGEARMAN 0",
        "#define HAVE_LIBINTL_H 1",
        "#define HAVE_LIBMEMCACHED 1",
        "#define HAVE_LIBMYSQL_BUILD 0",
        "#define HAVE_LIBPQ 0",
        "#define HAVE_LIMITS_H 1",
        "#define HAVE_MALLOC_H 1",
        "#define HAVE_MATH_H 1",
        "#define HAVE_MEMCACHED_BINARY 0",
        "#define HAVE_MEMCACHED_SASL_BINARY 0",
        "#define HAVE_MEMCHR 1",
        "#define HAVE_MEMMOVE 1",
        "#define HAVE_MEMORY_H 1",
        "#define HAVE_MEMSET 1",
        "#define HAVE_MSG_DONTWAIT 1",
        "#define HAVE_MURMUR_HASH 1",
        "#define HAVE_MYSQLD_BUILD 0",
        "#define HAVE_NETDB_H 1",
        "#define HAVE_NETINET_IN_H 1",
        "#define HAVE_NETINET_TCP_H 1",
        "#define HAVE_PIPE2 1",
        "#define HAVE_POLL_H 1",
        "#define HAVE_PTHREAD 1",
        "#define HAVE_PTHREAD_H 1",
        "#define HAVE_PTHREAD_PRIO_INHERIT 1",
        "#define HAVE_PTHREAD_TIMEDJOIN_NP 1",
        "#define HAVE_PTRDIFF_T 1",
        "#define HAVE_PUTENV 1",
        "#define HAVE_RCVTIMEO 1",
        "#define HAVE_SELECT 1",
        "#define HAVE_SETENV 1",
        "#define HAVE_SIGIGNORE 1",
        "#define HAVE_SNDTIMEO 1",
        "#define HAVE_SOCKET 1",
        "#define HAVE_SPAWN_H 1",
        "#define HAVE_STDARG_H 1",
        "#define HAVE_STDBOOL_H 1",
        "#define HAVE_STDDEF_H 1",
        "#define HAVE_STDINT_H 1",
        "#define HAVE_STDIO_H 1",
        "#define HAVE_STDLIB_H 1",
        "#define HAVE_STRCASECMP 1",
        "#define HAVE_STRCHR 1",
        "#define HAVE_STRDUP 1",
        "#define HAVE_STRERROR 1",
        "#define HAVE_STRERROR_R 1",
        "#define HAVE_STRINGS_H 1",
        "#define HAVE_STRING_H 1",
        "#define HAVE_STRSTR 1",
        "#define HAVE_STRTOL 1",
        "#define HAVE_STRTOUL 1",
        "#define HAVE_STRTOULL 1",
        "#define HAVE_SYSLOG_H 1",
        "#define HAVE_SYS_SOCKET_H 1",
        "#define HAVE_SYS_STAT_H 1",
        "#define HAVE_SYS_SYSCTL_H 1",
        "#define HAVE_SYS_TIME_H 1",
        "#define HAVE_SYS_TYPES_H 1",
        "#define HAVE_SYS_UN_H 1",
        "#define HAVE_SYS_WAIT_H 1",
        "#define HAVE_TIME_H 1",
        "#define HAVE_UNISTD_H 1",
        "#define HAVE_UUID_GENERATE_TIME_SAFE 0",
        "#define HAVE_UUID_UUID_H 0",
        "#define HAVE_VFORK 1",
        "#define HAVE_VISIBILITY 1",
        "#define HAVE_WORKING_FORK 1",
        "#define HAVE_WORKING_VFORK 1",
        "#define HAVE__BOOL 1",
        '#define HOST_CPU "x86_64"',
        '#define LT_OBJDIR ".libs/"',
        "#define MYSQLD_BINARY 0",
        "#define NDEBUG 1",
        '#define PACKAGE "libmemcached"',
        '#define PACKAGE_BUGREPORT "http://libmemcached.org/"',
        '#define PACKAGE_NAME "libmemcached"',
        '#define PACKAGE_STRING "libmemcached 1.0.18"',
        '#define PACKAGE_TARNAME "libmemcached"',
        '#define PACKAGE_URL ""',
        '#define PACKAGE_VERSION "1.0.18"',
        "#define STDC_HEADERS 1",
        "#ifndef _ALL_SOURCE",
        "# define _ALL_SOURCE 1",
        "#endif",
        "#ifndef _GNU_SOURCE",
        "# define _GNU_SOURCE 1",
        "#endif",
        "#ifndef _POSIX_PTHREAD_SEMANTICS",
        "# define _POSIX_PTHREAD_SEMANTICS 1",
        "#endif",
        "#ifndef _TANDEM_SOURCE",
        "# define _TANDEM_SOURCE 1",
        "#endif",
        "#ifndef __EXTENSIONS__",
        "# define __EXTENSIONS__ 1",
        "#endif",
        "#define VCS_CHECKOUT 0",
        '#define VCS_SYSTEM "none"',
        '#define VERSION "1.0.18"',
        "#define __STDC_LIMIT_MACROS 1",
        "#ifndef __cplusplus",
        "#endif",
        "#define restrict __restrict",
        "#if defined __SUNPRO_CC && !defined __RESTRICT",
        "# define _Restrict",
        "# define __restrict__",
        "#endif",
        "#ifndef HAVE_SYS_SOCKET_H",
        "# define SHUT_RD SD_RECEIVE",
        "# define SHUT_WR SD_SEND",
        "# define SHUT_RDWR SD_BOTH",
        "#endif",
        "#ifndef __STDC_FORMAT_MACROS",
        "#  define __STDC_FORMAT_MACROS",
        "#endif",
        "#if defined(__cplusplus) ",
        "#  include CINTTYPES_H ",
        "#else ",
        "#  include <inttypes.h> ",
        "#endif",
        "#if !defined(HAVE_ULONG) && !defined(__USE_MISC)",
        "# define HAVE_ULONG 1",
        "typedef unsigned long int ulong;",
        "#endif ",
        "#if defined(__APPLE__)",
        '#define HOST_OS "darwin19.4.0"',
        '#define HOST_VENDOR "apple"',
        "#else",
        '#define HOST_OS "linux-gnu"',
        "#define HOST_OS_LINUX 1",
        '#define HOST_VENDOR "unknown"',
        "#define STRERROR_R_CHAR_P 1",
        "#endif",
        "",
        "EOF",
    ]),
)
