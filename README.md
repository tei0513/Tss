    public static int[] completeCells(int[] cells, int days) {
        int pervious = 0;
        int[] newCells = new int[cells.length];
        for (int i = 0; i < days; i++) {
            for (int j = 0; j < cells.length; j++) {

                if (j == 0) {
                    if (cells[j + 1] == pervious) {
                        newCells[j] = 0;
                    } else {
                        newCells[j] = 1;
                    }
                } else if (j == cells.length - 1) {
                    if (cells[j - 1] == pervious) {
                        newCells[j] = 0;
                    } else {
                        newCells[j] = 1;
                    }
                } else {
                    if (cells[j - 1] == cells[j + 1]) {
                        newCells[j] = 0;
                    } else {
                        newCells[j] = 1;
                    }
                }
            }

            for (int k = 0; k < cells.length; k++) {
                cells[k] = newCells[k];
            }
        }

        return newCells;
    }
