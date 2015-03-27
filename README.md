public static void quickSort(int[] data, int i, int j){
    int p;
    if(i < j){
        p = partition(data, i, j);
        quickSort(data, i, p - 1);
        quickSort(data, p + 1, j);
    }
}
    
private static int partition(int[] data, int i, int j){
    int upper, lower, save;
    upper = i; lower = j; save = data[i];
    while(upper != lower){
        while(upper < lower && save <= data[lower]) lower--;
        if(upper != lower) data[upper] = data[lower];
        while(upper < lower && save >= data[upper]) upper++;
        if(upper != lower) data[lower] = data[upper];
    }
    data[upper] = save;
    return(upper);
}
