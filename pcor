import numpy as np
from scipy import stats, linalg

def pcorr(DF,k):
    C=DF.copy()
    val=list(C.columns.values)
    C[u'ones']=np.ones(C.shape[0])
    C = np.asarray(C)
    p = C.shape[1]
    P_corr = np.zeros((p-1, p-1), dtype=np.float)
    idx = np.zeros(p, dtype=np.bool)
    for kk in k:
      idx[kk] = True
    idx[p-1] = True
    for i in range(p-1):
        P_corr[i, i] = 1
        for j in range(i+1, p-1):
            beta_i = linalg.lstsq(C[:, idx], C[:, i])[0]
            beta_j = linalg.lstsq(C[:, idx], C[:, j])[0]

            res_j = C[:, j] - C[:, idx].dot(beta_j)
            res_i = C[:, i] - C[:, idx].dot(beta_i)
            
            corr = stats.pearsonr(res_i, res_j)[0]
            P_corr[i, j] = corr
            P_corr[j, i] = corr
    
    p=pd.DataFrame(P_corr, index=val, columns=val)
    return p
