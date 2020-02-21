########################################################################
# XMEN LAB                                                             #
# All Rights Reserved.                                                 #
#----------------------------------------------------------------------#
# Author: Thiago M. de Oliveira <thiago.oliveira@embedded.ufcg.edu.br> #
# Script: Makefile              Version : 0.1                          #
#                               Date    : 2020.02.21                   #
#----------------------------------------------------------------------#
# Description:                                                         #
#   SystemC model simulation Makefile.                                 #
#----------------------------------------------------------------------#
# Revision History:                                                    #
#   | Ver. | Date       | Author    | Description                    | #
#   | 0.1  | 2020.02.21 | Thiago M. | Initial version.               | #
########################################################################
BLOCK	= counter
SRC_DIR = ../src
TB_DIR = ../tb
SYSTEMC_HOME = /usr/local/systemc-2.3.3

run: compile
	./${BLOCK}

compile:
	@-g++ -I. -I${SYSTEMC_HOME}/include -L. -L${SYSTEMC_HOME}/lib-linux64 -Wl,-rpath=${SYSTEMC_HOME}/lib-linux64 -o ${BLOCK} ${TB_DIR}/${BLOCK}_tb.cpp ${SRC_DIR}/${BLOCK}.cpp -lsystemc -lm

waves: 
	@simvision -sst ${BLOCK}.vcd -input ${BLOCK}.svcf	&

clean:
	@-echo "Cleaning objects and local files..."
	@-rm ./${BLOCK}
	@-rm *.vcd *.svcf *.trn *.dsn
	@-rm -rf .simvision
