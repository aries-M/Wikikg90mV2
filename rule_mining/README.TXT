This code is from --- https://github.com/lajus/amie

step 1:
run python preprocess.py to generate sub-graphs of the data based on which rule-mining is performed.

step 2:
run
java -XX:-UseGCOverheadLimit -Xmx400G -jar amie-dev.jar './rules_input_file/train_hrt_0.txt'
java -XX:-UseGCOverheadLimit -Xmx400G -jar amie-dev.jar './rules_input_file/train_hrt_1.txt'
java -XX:-UseGCOverheadLimit -Xmx400G -jar amie-dev.jar './rules_input_file/train_hrt_2.txt'
java -XX:-UseGCOverheadLimit -Xmx400G -jar amie-dev.jar './rules_input_file/train_hrt_3.txt'
java -XX:-UseGCOverheadLimit -Xmx400G -jar amie-dev.jar './rules_input_file/train_hrt_4.txt'
to generate the rules mined from the sub-graphs.

step 3:
run python parse_rules.py to generate new triplets based on the mined rules.

step 4:
run python create_rule_mining_candidate.py to generate rule-mining candidates for every query in test-dev.

step 5:
run python load_hr2t.py to tailor the candidate size to 50 for every query.

