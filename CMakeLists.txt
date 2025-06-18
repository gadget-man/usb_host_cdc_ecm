set(REQUIRES_COMPONENTS usb esp_event esp_netif esp_eth)

if(CONFIG_MDNS_PREDEF_NETIF_ETH)
    list(APPEND REQUIRES_COMPONENTS mdns)
endif()

idf_component_register(SRCS "cdc_ecm_host.c" "cdc_host_descriptor_parsing.c"
                       INCLUDE_DIRS "include"
                       PRIV_INCLUDE_DIRS "private_include"
                       REQUIRES ${REQUIRES_COMPONENTS})
