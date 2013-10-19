[
{ "autoconf": {
    "name": "curl_gen",
    "configure_env": [ "USER_CXXFLAGS=\"-Wno-unused-local-typedefs -Wno-unused-function -Wno-error=deprecated-declarations\"", "USER_LDFLAGS=-lcurl" ],
    "configure_args": [ "--enable-warnings=false",
                        "--enable-ewarning=false",
                        "--with-boost=$ROOT_DIR/$BOOST_ROOT"
    ],
    "dependencies": [ "../boost:boost" ],
    "outs": [ "$GEN_DIR/lib/libcurlpp.a", "$GEN_DIR/lib/libutilspp.a" ],
    "licenses": [ "http://opensource.org/licenses/mit-license.php" ]
} },
{ "cc_library": {
    "name": "curlpp",
    "cc_objects": [ "$GEN_DIR/lib/libcurlpp.a", "$GEN_DIR/lib/libutilspp.a" ],
    "strict_file_mode": false,
    "dependencies": [ ":curl_gen" ],
    "cc_linker_args": [ "-lcurl" ],  // required system library
    "header_compile_args": [ "-I$GEN_DIR/include", "-Wno-comment" ]
} }
]