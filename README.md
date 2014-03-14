elasticsearch-rpms
==================

This is a clone of tavisto's excellent [elasticsearch-rpms] repo with some Mozilla-specific modifications.

Instructions
------------

 * Check out the latest revision of this repo.

    <pre>git clone --depth=1 https://github.com/phrawzty/elasticsearch-rpms.git</pre>

 * Create your rpmbuild directory

    <pre>rpmdev-setuptree</pre>

 * Sym link all the sources and spec files into your build tree
    
    <pre>export repo=`pwd`/elasticsearch-rpms
    cd rpmbuild
    ln -s ${repo}/SPECS/elasticsearch.spec SPECS/elasticsearch.spec 
    ln -s ${repo}/SOURCES/* SOURCES/</pre>

 * Download and position the ES source tarball

    <pre>spectool -g SPECS/elasticsearch.spec
    mv elasticsearch*.tar.gz SOURCES/</pre>

 * Build the RPMs

    <pre>rpmbuild -ba --nodeps SPECS/elasticsearch.spec</pre>

[elasticsearch-rpms]: https://github.com/tavisto/elasticsearch-rpms
