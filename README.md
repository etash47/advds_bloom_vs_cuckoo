# How to use this
## Testing the Bloom Filter
- Implementation Details are in `bloom_filter.py`
- Test functions are in `main.py`

To view the empirical analysis of ONLY bloom filters, comment lines 108-111 in `main.py` and run interpreter main on `main.py`
To view the empirical analysis of Bloom vs. Cuckoo filters, run interpreter main on `main.py`

To adjust the hash functions used for Bloom filters, define `hash_fxns` in `main.py/analyze_bloom_filter()` as some set of hash functions or lambdas. Then, call `bloomFilter = bloom_filter.BloomFilter(m, k, hash_fxns)` to create a new bloomFilter. Be sure to adjust m and k based on the number you are planning to insert. 

To insert without our prebuilt experiments, `bloomFilter.insert_with_time_elapsed`
To check without our prebuilt experiments, `bloomFilter.check_with_false_prob_and_time_elapsed`

Adjust `inserting_num = 3800 #2**11` `num_random_checks = 500` for prebuilt goals. Be sure to adjust `m` and `k` as well based on k = (m/n)*ln(2).

`goal_1_theoretial_false_pos_rate` tests theoretical rate of insertion on a bloomFilter.
`goal_2_polynomial_hash` tests empirical rate of polynomial hashing on bloomFilter.
`goal_3_polynomial_hash` tests insertion speed on bloomFilter.

## Testing the Cuckoo Filter
- Implementation is located in `cuckoo_filter.py`
- Test functions are in `test_cuckoo_filter.py`

To view the empirical analysis of ONLY cuckoo filters, run interpreter on `test_cuckoo_filter.py`.

To adjust the fingerprint size when testing the false positive rates, assign `f` to be your desired value in the `main()` function (recommended range of `f` is 4-20 bits). 

Within both tests:
- to adjust the size of the cuckoo filter, set `M` to desired value (must be a power of 2). 
- to adjust the number of elements inserted in the table, set `n` to desired value.
