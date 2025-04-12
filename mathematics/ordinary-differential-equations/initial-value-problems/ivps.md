<pre>
    Solve an ordinary differential equation using the Backward Euler method.

    Parameters
    ----------
    odeqtn : {str, symbolic, list_like, callable}
        The ODE equation to be integrated numerically.
    time_span : list_like
        Start and end time points (lower and upper limits of 
        integration).
    y0 : {int, float, list_like}
        Initial value(s) of the ODE or system of ODEs.
    exactsol : {None, str, symbolic, Callable}, (default=None)
        The exact solution of the ODE.
    stepsize : float, optional (default=None)
        The interval (difference between two consecutive time points).
    nsteps : int, optional (default=10)
        Number of steps (time points).
    maxit : int, optional (default=10)
        Maximum number of iterations.
    show_iters : int, optional (default=None)
        Integer representing the number of iterations to be displayed.
        Valid values: None or 1 <= x <= n. If None, then all 
        iterations are displayed.
    auto_display : bool, optional (default=True)
        If \`True\`, results will be displayed automatically.
    decimal_points : int, optional (default=8)
        Number of decimal points or significant figures for symbolic expressions.

    Returns
    -------
    table : pandas.DataFrame
        A DataFrame with the tabulated results.
    dframe : pandas.Styler
        Above table with answer highlighted.
    float
        The numerical solution of the ODE.

    Examples
    --------
    >>> import stemlab as stm
    >>> f = 'y - t^2 + 1'
    >>> ft = '(t + 1)^2 - 0.5 * exp(t)'
    >>> a, b = (0, 2)
    >>> y0 = 0.5
    >>> result = stm.ivps_beuler(odeqtn=f, exactsol=ft,
    ... time_span=[a, b], y0=y0, decimal_points=14)
    
        Time (t)  Approximated (yi)  Exact solution(y)  Error: | y - yi |
    0        0.0   0.50000000000000   0.50000000000000   0.00000000000000
    1        0.2   0.86500000000000   0.82929862091992   0.03570137908008
    2        0.4   1.29125000000000   1.21408765117936   0.07716234882064
    3        0.6   1.77406250000000   1.64894059980475   0.12512190019525
    4        0.8   2.30757812500000   2.12722953575377   0.18034858924623
    5        1.0   2.88447265625000   2.64085908577048   0.24361357047952
    6        1.2   3.49559082031250   3.17994153863173   0.31564928168077
    7        1.4   4.12948852539062   3.73240001657766   0.39708850881296
    8        1.6   4.77186065673828   4.28348378780244   0.48837686893584
    9        1.8   5.40482582092285   4.81517626779352   0.58964955312933
    10       2.0   6.00603227615356   5.30547195053468   0.70056032561889
    
    Answer = 6.00603227615356
  </pre>
