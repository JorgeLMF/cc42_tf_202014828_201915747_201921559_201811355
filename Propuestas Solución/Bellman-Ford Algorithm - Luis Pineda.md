# Bellman-Ford Algorithm

El algoritmo Bellman-Ford es un algoritmo muy similar en funcionalidad al algoritmo de Dijkstra, en el sentido que permite hallar el camino más corto desde un único vertice hacia todos los demas vértices de un grafo dirigido. A pesar de ser efectivamente menos eficiente en tiempo de cómputo que el algoritmo de Dijkstra, ofrece mucha mayor versatilidad al aceptar pesos negativos para las aristas del grafo, detectando ciclos negativos en el mismo.

## Complejidad algorítmica

A diferencia del algoritmo Dijkstra cuya complejidad es de O(n^2), el algoritmo Bellman-Ford tiene una complejidad de O(VE), donde V es el numero de vertices en el grafo y E el numero de aristas. En grafos completos en los que E=n^2, la complejidad del algoritmo Bellman-Ford (VE) tiende a ser O(n^3).

## Pseudocódigo 
```
  Bellman_Ford(grafo G, nodo_origen nd)
      para v en V[G]:
          distancia[v]=INFINITO
          padre[v]=NULO
      finPara
      distancia[s]=0
      para i=1 hasta |v[G]|-1:
          para (u,v) en E[G]:
              si distancia[v] > distancia[u] + peso(u, v):
                  distancia[v] = distancia[u] + peso (u,v)
                  padre[v] = u
              finSi
          finPara
      finPara
      para (u, v) en E[G]:
          si distancia[v] > distancia[u] + peso(u, v):
              retorna FALSO
          finSi
      finPara
      retorna VERDADERO 
  FinBellman_Ford
```

