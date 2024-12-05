def merge_sort(arr):
    """
    Ordena uma lista usando o algoritmo Merge Sort.

    :param arr: Lista de elementos a serem ordenados.
    :return: A lista ordenada.
    """
    if len(arr) <= 1:
        return arr

    # Divide a lista ao meio
    mid = len(arr) // 2
    left_half = merge_sort(arr[:mid])
    right_half = merge_sort(arr[mid:])

    # Mescla as duas metades ordenadas
    return merge(left_half, right_half)


def merge(left, right):
    """
    Mescla duas listas ordenadas em uma única lista ordenada.

    :param left: Primeira lista ordenada.
    :param right: Segunda lista ordenada.
    :return: Lista resultante da mesclagem.
    """
    merged = []
    i = j = 0

    # Compara elementos de ambas as listas e adiciona o menor à lista final
    while i < len(left) and j < len(right):
        if left[i] < right[j]:
            merged.append(left[i])
            i += 1
        else:
            merged.append(right[j])
            j += 1

    # Adiciona os elementos restantes
    merged.extend(left[i:])
    merged.extend(right[j:])

    return merged


# Testes
if __name__ == "__main__":
    data = [38, 27, 43, 3, 9, 82, 10]
    print("Lista original:", data)
    sorted_data = merge_sort(data)
    print("Lista ordenada:", sorted_data)
# 6.-Merge-Sort
