#!/bin/bash
# this is a script related feature
# if you want to view the resulting file, 
#  you need to comment out the last line.

# view feature text
copy-feats ark:sample/foo_ori.ark ark,t:foo_txt.ark

: << 'RESULT1'
fe_03_00047-A-025005-025135  [
  55.45902 -24.94659 2.914925 -9.31487 -15.19995 -18.27135 -20.55405 -9.791942 -14.11931 17.55075 -2.651924 2.889459 3.196146 
  55.99312 -24.94659 3.864424 -14.36781 -13.30569 -18.53551 -5.728525 -4.950411 -13.866 10.23212 -15.69991 2.889459 -3.566411 
RESULT1


# view paste feature
copy-feats "ark:select-feats 0-1 ark:foo_txt.ark ark,t:- |" ark,t:foo_sub.ark
paste-feats ark:foo_txt.ark ark:foo_sub.ark ark,t:paste_foo_txt_sub.ark

: << 'RESULT2'
fe_03_00047-A-025005-025135  [
  55.45902 -24.94659 2.914925 -9.31487 -15.19995 -18.27135 -20.55405 -9.791942 -14.11931 17.55075 -2.651924 2.889459 3.196146 55.45902 -24.94659 
  55.99312 -24.94659 3.864424 -14.36781 -13.30569 -18.53551 -5.728525 -4.950411 -13.866 10.23212 -15.69991 2.889459 -3.566411 55.99312 -24.94659 
RESULT2


# view append feature
append-vector-to-feats ark:foo_txt.ark ark:sample/foo_vec.ark ark,t:append_foo_txt_vec.ark

: << 'RESULT3'
fe_03_00047-A-025005-025135  [
  55.45902 -24.94659 2.914925 -9.31487 -15.19995 -18.27135 -20.55405 -9.791942 -14.11931 17.55075 -2.651924 2.889459 3.196146 100 
  55.99312 -24.94659 3.864424 -14.36781 -13.30569 -18.53551 -5.728525 -4.950411 -13.866 10.23212 -15.69991 2.889459 -3.566411 100 
RESULT3


# view cmvn stats
compute-cmvn-stats ark:sample/ex_cmvn.ark ark,t:ex_cmvn.stats

: << 'RESULT4'
fe_03_00047-A-026306-026426  [
  4 8 12 16 20 4 
  4 16 36 64 100 0 ]
RESULT4

rm -f foo_txt.ark foo_sub.ark paste_foo_txt_sub.ark append_foo_txt_vec.ark ex_cmvn.stats

