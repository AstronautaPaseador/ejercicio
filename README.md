# ejercicio

    public static ArrayList<Integer> obtenerCodigoEmpleados(ArrayList<Integer> listaCodigos) {
        Object[] st = listaCodigos.toArray();
        for (Object s : st) {
            if (listaCodigos.indexOf(s) != listaCodigos.lastIndexOf(s)) {
                listaCodigos.remove(listaCodigos.lastIndexOf(s));
            }
        }
        return listaCodigos;
    }

    public static ArrayList<Integer> obtenerPosicionFaltantes(ArrayList<Integer> listaPosicion, ArrayList<Integer> listaCodigos, Integer codigosFaltantes) {
        ArrayList<Integer> lista2 = new ArrayList<Integer>();
        for (int i = 0; i < listaPosicion.size(); i++) {

            if (listaCodigos.get(listaPosicion.get(i)).equals(codigosFaltantes)) {
                lista2.add(listaPosicion.get(i));
            }
        }

        return lista2;
    }

    public static ArrayList<Integer> obtenerCodigosFaltantes(ArrayList<Integer> listaCodigosA, ArrayList<Integer> listaCodigosB) {

        ArrayList<Integer> lista3 = new ArrayList<Integer>();
        
        if (listaCodigosB.size() < listaCodigosA.size()) {
            for (int i = 0; i < listaCodigosB.size()+(listaCodigosA.size()-listaCodigosB.size()); i++) {

                if (!listaCodigosB.contains(listaCodigosA.get(i))) {
                    lista3.add(listaCodigosA.get(i));
                }
            }
        }else{
            for (int i = 0; i < listaCodigosA.size(); i++) {

                if (!listaCodigosB.contains(listaCodigosA.get(i))) {
                    lista3.add(listaCodigosA.get(i));
                }
            }
        }
        return lista3;

    }

    public static Integer obtenerNumeroIntercambios(ArrayList<Integer> listaCodigosA, ArrayList<Integer> listaCodigosB) {

        int count1 = 0;
        int count2 = 0;

        for (int i = 0; i < listaCodigosB.size(); i++) {
            if (!listaCodigosA.contains(listaCodigosB.get(i))) {
                count1 = count1 + 1;
            }
        }
        for (int i = 0; i < listaCodigosA.size(); i++) {
            if (!listaCodigosB.contains(listaCodigosA.get(i))) {
                count2 = count2 + 1;
            }
        }
        if (count1 > count2) {
            return count2;
        } else {
            return count1;
        }
    }
