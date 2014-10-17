# sshd
#
# VERSION               0.0.1

FROM     sshd:14.04
MAINTAINER hongbo.mo "hongbo.mo@upai.com"

RUN wget -O /tmp/GraphicsMagick-1.3.18.tar.gz http://softlayer-dal.dl.sourceforge.net/project/graphicsmagick/graphicsmagick/1.3.18/GraphicsMagick-1.3.18.tar.gz \
    && tar -zxvf /tmp/GraphicsMagick-1.3.18.tar.gz -C /tmp

RUN cd /tmp/GraphicsMagick-1.3.18 && \
sed -i 's/O2/O0/' ./configure && \        
./configure --prefix=/usr/local --enable-shared --with-quantum-depth=16 --with-gs-font-dir=default \
--with-windows-font-dir=/usr/local/lib/GraphicsMagick-1.3.18/config/fonts && make && make install 
RUN ldconfig

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
