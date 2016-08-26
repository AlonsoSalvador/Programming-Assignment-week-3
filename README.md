# Programming-Assignment-week-3


## Write a short comment describing this function

makeVector <- function(x = matrix()) {
    m <- NULL
    set <- function(y) {
        x <<- y
        m <<- NULL
    }
    get <- function() x
    setmean <- function(inverse) m <<- inverse
    getmean <- function() m
    list(set = set, get = get,
    setmean = setmean,
    getmean = getmean)
}



## Write a short comment describing this function

cachemean <- function(x, ...) {
    m <- x$getmean()
    if(!is.null(m)) {
        message("getting cached data")
        return(m)
    }
    data <- x$get()
    m <- solve(data, ...)
    x$setmean(m)
    return(m)
}
