## our aim in this function is to write a pair of function, namely, 
##"makeCacheMatrix" and "cacheSolve" that cache the inverse of the matrix
 ##makeCacheMatrix is a function which creates a special "matrix" object that can 
##cache its inverse for the input (which is an invertible square matrix) 
 
makeCacheMatrix <- function(x = matrix()) {  
j <- NULL   
set <- function(y){   
x <<- y   
j <<- NULL   
}   
get <- function()x   
setInverse <- function(inverse) j <<- inverse   
getInverse <- function() j   
list(set = set, get = get,   
setInverse = setInverse,   
getInverse = getInverse) 
} 
 ##cacheSolve is a function which computes the inverse of the special "matrix" 
##returned by makeCacheMatric above. If the inverse has already been calculated 
##(and the matrix has not changed), then the cachesolve should retrieve the 
##inverse from the cache cacheSolve <- function(x, ...) { 
## Return a matrix that is the inverse of 'x'  
j <- x$getInverse()   
if(!is.null(j)){   
message("getting cached data")   
return(j)   
}   
mat <- x$get()  
 j <- solve(mat,...)  
x$setInverse(j)   
j 
}
