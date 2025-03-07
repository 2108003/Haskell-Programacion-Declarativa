# Haskell-Programacion-Declarativa
'''Haskell
-- Definimos una estructura de datos para representar los libros
data Libro = Libro {
    titulo :: String,
    genero :: String
} deriving (Show)

-- Base de datos de libros
biblioteca :: [Libro]
biblioteca = [
    Libro "1984" "Ciencia Ficción",
    Libro "Fahrenheit 451" "Ciencia Ficción",
    Libro "El Hobbit" "Fantasía",
    Libro "Drácula" "Terror",
    Libro "It" "Terror",
    Libro "Orgullo y Prejuicio" "Romance"
    ]

-- Función para recomendar libros según el género deseado
recomendarLibros :: String -> [Libro]
recomendarLibros generoDeseado = filter (\libro -> genero libro == generoDeseado) biblioteca

-- Función principal que ejecuta el programa
main :: IO ()
main = do
    putStrLn "Introduce un género literario (Ciencia Ficción, Fantasía, Terror, Romance):"
    generoUsuario <- getLine
    let librosRecomendados = recomendarLibros generoUsuario
    if null librosRecomendados
        then putStrLn "No hay recomendaciones para ese género."
        else do
            putStrLn "Libros recomendados:"
            mapM_ (putStrLn . titulo) librosRecomendados
'''
