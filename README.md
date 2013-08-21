cjdnsify
========

About: A script that allows you to run programs bound exclusively to your cjdns connection

Requirements: This script utilizes the powerful force_bind library, located @ http://kernel.embedromix.ro/us/

Usage:
    1. Copy cjdnsify.conf to /etc/default/cjdnsify
    2. Configure the location of force_bind.so and the tun device connected to cjdns in /etc/default/cjdnsify
    3. Assuming cjdns has an address associated with the tun device you configured it to use, run: cjdnsify program

Note: Not all programs allow force_bind to dictate which address space they can access, and therefore cjdnsify will not work with all programs; you should always test first!
