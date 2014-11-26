Relais-via-PDS
==============

Login to Relais for Inter-Library loans using Ex Libris' PDS

NAME
    illrequest

SYNOPSIS
        http://.../cgi-bin/illrequest

DESCRIPTION
    Redirects to our ILL request form (Relais), after first retrieving
    username from PDS. It is assumed that this script is run on return from
    a PDS login, i.e. from the URL:

        https://primo-direct-apac.hosted.exlibrisgroup.com/pds
        ?func=load-login&institute=61ADELAIDEU&calling_system=primo&lang=eng
        &url=http://systems.library.adelaide.edu.au/cgi/illredirect

    If not, then script will just redirect to the login page.

    Username is obtained by calling PDS back with the bor-info function,
    which should return an XML data structure like so:

        <bor>
            <bor_id>
                <id>1234567</id>
                <handle>6820141643591607825054665244825</handle>
                <institute>61ADELAIDE_INST</institute>
            </bor_id>
            <bor-info>
                <id>1234567</id>
                <id>Stephen</id>
                <institute>61ADELAIDE_INST</institute>
                <name>Stephen</name>
                <group>STAFF</group>
                <email_address>stephen.thomas@adelaide.edu.au</email_address>
            </bor-info>
        </bor>

    We're only interested in the <id>, which is then passed to Relais in the
    PI and RK fields.

AUTHOR
    Steve Thomas <stephen.thomas@adelaide.edu.au>

VERSION
    This is version 2014.11.26

LICENCE
    Copyright 2014 Steve Thomas

    Permission is hereby granted, free of charge, to any person obtaining a
    copy of this software and associated documentation files (the
    "Software"), to deal in the Software without restriction, including
    without limitation the rights to use, copy, modify, merge, publish,
    distribute, sublicense, and/or sell copies of the Software, and to
    permit persons to whom the Software is furnished to do so, subject to
    the following conditions:

    The above copyright notice and this permission notice shall be included
    in all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
    OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
    MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
    IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY
    CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,
    TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
    SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

