<div class="image-logo"><img src="/img/image-logos/nzbhydra2.svg" alt="logo"></div>

[:octicons-mark-github-16: GitHub](https://github.com/hotio/nzbhydra2){: .header-icons target=_blank rel="noopener noreferrer" }  
[:octicons-container-16: docker.io](https://hub.docker.com/r/hotio/nzbhydra2){: .header-icons target=_blank rel="noopener noreferrer" }
 / [:octicons-container-16: ghcr.io](https://github.com/orgs/hotio/packages/container/package/nzbhydra2){: .header-icons target=_blank rel="noopener noreferrer" }
 / [:octicons-container-16: quay.io](https://quay.io/repository/hotio/nzbhydra2){: .header-icons target=_blank rel="noopener noreferrer" }  
[:octicons-link-16: NZBHydra2](https://github.com/theotherp/nzbhydra2){: .header-icons target=_blank rel="noopener noreferrer" }  

--8<-- "includes/stats.md"

## Starting the container

!!! docker ""

    === "cli"

        ```shell
        docker run --rm \
            --name nzbhydra2 \
            -p 5076:5076 \
            -e PUID=1000 \
            -e PGID=1000 \
            -e UMASK=002 \
            -e TZ="Etc/UTC" \
            -v /<host_folder_config>:/config \
            cr.hotio.dev/hotio/nzbhydra2
        ```

    === "compose"

        ```yaml
        version: "3.7"

        services:
          nzbhydra2:
            container_name: nzbhydra2
            image: cr.hotio.dev/hotio/nzbhydra2
            ports:
              - "5076:5076"
            environment:
              - PUID=1000
              - PGID=1000
              - UMASK=002
              - TZ=Etc/UTC
            volumes:
              - /<host_folder_config>:/config
        ```

--8<-- "includes/tags.md"
