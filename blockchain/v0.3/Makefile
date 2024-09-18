# Compiler and flags
CC = gcc
CFLAGS = -Wall -Werror -Wextra -pedantic -std=gnu90 -ggdb3 -c -I. -Itransaction/ -Iprovided/ -I../../crypto -L../../crypto -lhblk_crypto -lllist -lssl -lcrypto -pthread

# Source files
SRC0 = blockchain_create.c blockchain_deserialize.c blockchain_destroy.c \
       blockchain_difficulty.c blockchain_serialize.c \
       transaction/transaction_create.c transaction/transaction_destroy.c

# Object files
OBJ0 = $(SRC0:.c=.o)

# Output library name
NAME0 = libhblk_blockchain.a

# Phony targets (not real files)
.PHONY: clean oclean fclean libhblk_blockchain.a

# Target to build the static library
libhblk_blockchain.a: blockchain.h transaction/transaction.h $(OBJ0)
	ar rcs $(NAME0) $(OBJ0)

# Clean object files and output library
clean:
	$(RM) *~ $(NAME0)

# Clean object files
oclean:
	$(RM) $(OBJ0)

# Full clean of object files and output library
fclean: clean oclean

