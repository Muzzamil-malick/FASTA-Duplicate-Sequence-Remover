# Load necessary libraries
library(seqinr)

# Function to remove duplicate sequences from a FASTA file
remove_duplicate_sequences <- function(input_file, output_file) {
  # Read FASTA file
  fasta <- read.fasta(input_file)
  
  # Find unique sequence identifiers
  unique_ids <- unique(names(fasta))
  
  # Create a new list to store unique sequences
  unique_fasta <- list()
  
  # Loop through unique identifiers and keep only one record of each
  for (id in unique_ids) {
    # Find index of the first occurrence of the sequence
    index <- which(names(fasta) == id)[1]
    # Add sequence to the new list
    unique_fasta[[id]] <- fasta[[index]]
  }
  
  # Write unique sequences to a new FASTA file
  write.fasta(sequences = unique_fasta, names = unique_ids, file = output_file)
}

# Choose input and output files interactively
input_file <- file.choose()
output_file <- file.choose()

# Remove duplicate sequences
remove_duplicate_sequences(input_file, output_file)

cat("Duplicate sequences removed and saved to", output_file, "\n")
