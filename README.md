# CoreferentMentionRetrieval
This is the test collection for the task of Coreferent Mention Retrieval defined by Sankepally et al. in "A Test Collection for Coreferent Mention Retrieval." ACM SIGIR 2018. <br>
Following are the file names and their contents:
<ul>
  <li><b>doc_ids.txt </b> : The Document IDs from the subset of documents in the TAC 2014 EDL collection (LDC catalog number: LDC2014E13)</li>
  <li><b>doc_sentence_char_offsets.tar.gzt</b> : This compressed file contains file with sentence boundaries. When uncompressed it is 150MBs in size. Character offsets for the sentence boundaries for all documents in doc_ids.txt are specified in this format: [docid]:sentence_start_offset:sentence_ending_offset [unique sentence identifier]. </li>
  <li><b>CMR_char_offset_queries.txt </b>: Each line has a mention query in the following format: <br> [query ID] [query type] [doc_id:sentence_start_offset:sentence_ending_offset:token_start_offset:token_ending_offset] [query mention string]</li>
  <li><b>CMR_char_offset_qrels.txt</b>: Each line has a mention query in the following format: <br>[query ID]    [query type]     [doc_id:sentence_start_offset:sentence_ending_offset]    [binary relevance judgment] </li>
 
  </ul>
  
  # Evaluation
  You can use the latest <a href="https://trec.nist.gov/trec_eval/">trec_eval</a> for evaluation.<br>
  After making sure your results file is in TREC format and has no duplicate lines, you can run:<br>
  ./trec_eval -q -M100 -m infAP batch2_char_offset_qrels.txt [your_result_file_name]
  
