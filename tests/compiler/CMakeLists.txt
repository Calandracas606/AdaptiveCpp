configure_file(lit.site.cfg.py.in lit.site.cfg.py @ONLY)
add_custom_target(check-cbs
        COMMAND lit "${CMAKE_CURRENT_BINARY_DIR}/cbs" -v)
add_custom_target(check-sscp
        COMMAND lit "${CMAKE_CURRENT_BINARY_DIR}/sscp" -v)

add_custom_target(check)
add_dependencies(check check-cbs check-sscp)