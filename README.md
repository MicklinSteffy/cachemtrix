# cachemtrix
# R-wk3-assignment
makecachematrix <- function(x = matrix(sample(1:100,9),3,3)) {
  s <- NULL
  set <- function(y) {
    x <<- y
    s <<- NULL
  }
  get <- function() x
  setmean <- function(solve) s <<- solve
  getmean <- function() s
  list(set = set, get = get,
       setsolve = setsolve,
       getsolve = getsolve)
}


#2 cachesolve
#week3_assignment

cacheSolve <- function(x, ...) {
  s <- x$getsolve()
  if(!is.null(s)) {
    message("getting inversed matrix")
    return(s)
  }
  data <- x$get()
  s <- solve(data, ...)
  x$setsolve(s)
  s
}
