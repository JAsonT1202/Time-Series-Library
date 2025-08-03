1. Custom Dataset
`     

    cols = list(df_raw.columns)

    if 'date' in cols:
        cols.remove('date')
    if self.target and self.target in cols:
        cols.remove(self.target)
        df_raw = df_raw[['date'] + cols + [self.target]]
    else:
        df_raw = df_raw[['date'] + cols]

    num_train = int(len(df_raw) * 0.7)
    num_test = int(len(df_raw) * 0.2)
    
    
`

2. 
