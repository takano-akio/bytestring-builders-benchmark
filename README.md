# Summary

This project exists purely for research purposes of determining the optimal way of building strict bytestrings. As a result of this project some library may be released (depending on the outcome). The ideas behind this project stem from [a discussion on Reddit](https://www.reddit.com/r/haskell/comments/3qj53a/an_alternative_bytestring_builder/).

If you know any way of optimizing any particular benchmark or can suggest another benchmark subject, instead of complaining, PR without hesitation! This is intended to be a community project.

# Current results

    benchmarking Small Input/Main.BufferBuilderMonoid
    time                 714.6 ns   (703.1 ns .. 730.3 ns)
                         0.990 R²   (0.983 R² .. 0.995 R²)
    mean                 787.4 ns   (754.2 ns .. 843.7 ns)
    std dev              147.2 ns   (91.03 ns .. 249.4 ns)
    variance introduced by outliers: 97% (severely inflated)

    benchmarking Small Input/Main.Concat
    time                 753.1 ns   (723.8 ns .. 784.5 ns)
                         0.989 R²   (0.985 R² .. 0.996 R²)
    mean                 772.2 ns   (741.1 ns .. 825.3 ns)
    std dev              130.5 ns   (90.14 ns .. 202.0 ns)
    variance introduced by outliers: 96% (severely inflated)

    benchmarking Small Input/Main.Seq
    time                 421.4 ns   (414.1 ns .. 428.8 ns)
                         0.998 R²   (0.998 R² .. 0.999 R²)
    mean                 420.3 ns   (416.7 ns .. 425.7 ns)
    std dev              15.30 ns   (13.16 ns .. 18.23 ns)
    variance introduced by outliers: 53% (severely inflated)

    benchmarking Small Input/Main.DList
    time                 447.3 ns   (437.1 ns .. 461.9 ns)
                         0.987 R²   (0.979 R² .. 0.994 R²)
    mean                 504.0 ns   (483.0 ns .. 539.5 ns)
    std dev              105.4 ns   (77.35 ns .. 146.2 ns)
    variance introduced by outliers: 98% (severely inflated)

    benchmarking Small Input/Main.DListWithSize
    time                 556.3 ns   (529.2 ns .. 582.1 ns)
                         0.990 R²   (0.985 R² .. 0.994 R²)
    mean                 546.9 ns   (533.4 ns .. 563.8 ns)
    std dev              54.20 ns   (43.50 ns .. 66.10 ns)
    variance introduced by outliers: 90% (severely inflated)

    benchmarking Small Input/Main.BinaryTree, thru list
    time                 368.7 ns   (350.3 ns .. 387.0 ns)
                         0.982 R²   (0.971 R² .. 0.993 R²)
    mean                 413.4 ns   (359.1 ns .. 567.0 ns)
    std dev              330.5 ns   (37.23 ns .. 633.8 ns)
    variance introduced by outliers: 100% (severely inflated)

    benchmarking Small Input/Main.BinaryTree, explicit allocation
    time                 1.738 μs   (1.685 μs .. 1.801 μs)
                         0.990 R²   (0.982 R² .. 0.996 R²)
    mean                 1.939 μs   (1.738 μs .. 2.690 μs)
    std dev              1.237 μs   (108.5 ns .. 2.629 μs)
    variance introduced by outliers: 99% (severely inflated)

    benchmarking Small Input/Main.BinaryTreeWithSize
    time                 375.5 ns   (369.3 ns .. 382.7 ns)
                         0.998 R²   (0.997 R² .. 0.999 R²)
    mean                 381.3 ns   (376.9 ns .. 386.1 ns)
    std dev              15.55 ns   (12.16 ns .. 20.63 ns)
    variance introduced by outliers: 59% (severely inflated)

    benchmarking Small Input/FastBuilder
    time                 410.6 ns   (405.5 ns .. 417.3 ns)
                         0.998 R²   (0.997 R² .. 0.999 R²)
    mean                 412.3 ns   (407.9 ns .. 418.0 ns)
    std dev              19.08 ns   (15.56 ns .. 23.25 ns)
    variance introduced by outliers: 65% (severely inflated)

    benchmarking Small Input/Main.ListT
    time                 677.9 ns   (667.1 ns .. 691.4 ns)
                         0.997 R²   (0.996 R² .. 0.998 R²)
    mean                 705.3 ns   (692.9 ns .. 723.7 ns)
    std dev              50.50 ns   (42.22 ns .. 60.95 ns)
    variance introduced by outliers: 81% (severely inflated)

    benchmarking Small Input/List
    time                 346.8 ns   (339.3 ns .. 356.0 ns)
                         0.996 R²   (0.993 R² .. 0.998 R²)
    mean                 352.3 ns   (344.7 ns .. 359.5 ns)
    std dev              25.87 ns   (18.90 ns .. 33.29 ns)
    variance introduced by outliers: 82% (severely inflated)

    benchmarking Small Input/Data.ByteString.Builder
    time                 903.4 ns   (879.7 ns .. 930.8 ns)
                         0.996 R²   (0.994 R² .. 0.998 R²)
    mean                 883.5 ns   (871.6 ns .. 901.0 ns)
    std dev              43.31 ns   (34.52 ns .. 52.01 ns)
    variance introduced by outliers: 66% (severely inflated)

    benchmarking Small Input/Data.ByteString
    time                 289.0 ns   (281.6 ns .. 299.0 ns)
                         0.993 R²   (0.989 R² .. 0.997 R²)
    mean                 285.1 ns   (278.7 ns .. 293.3 ns)
    std dev              24.22 ns   (18.59 ns .. 34.10 ns)
    variance introduced by outliers: 87% (severely inflated)

    benchmarking Large Input/Main.BufferBuilderMonoid
    time                 169.3 μs   (166.4 μs .. 172.8 μs)
                         0.997 R²   (0.996 R² .. 0.999 R²)
    mean                 169.0 μs   (167.5 μs .. 170.8 μs)
    std dev              5.735 μs   (4.253 μs .. 7.798 μs)
    variance introduced by outliers: 31% (moderately inflated)

    benchmarking Large Input/Main.Concat
    time                 6.635 ms   (6.354 ms .. 7.013 ms)
                         0.975 R²   (0.946 R² .. 0.995 R²)
    mean                 7.141 ms   (6.912 ms .. 7.745 ms)
    std dev              953.7 μs   (573.3 μs .. 1.617 ms)
    variance introduced by outliers: 71% (severely inflated)

    benchmarking Large Input/Main.Seq
    time                 637.8 μs   (615.3 μs .. 658.5 μs)
                         0.989 R²   (0.983 R² .. 0.996 R²)
    mean                 608.8 μs   (594.9 μs .. 631.6 μs)
    std dev              60.44 μs   (38.25 μs .. 99.40 μs)
    variance introduced by outliers: 75% (severely inflated)

    benchmarking Large Input/Main.DList
    time                 381.6 μs   (366.6 μs .. 403.3 μs)
                         0.982 R²   (0.969 R² .. 0.995 R²)
    mean                 389.5 μs   (381.4 μs .. 404.6 μs)
    std dev              34.73 μs   (21.52 μs .. 58.64 μs)
    variance introduced by outliers: 73% (severely inflated)

    benchmarking Large Input/Main.DListWithSize
    time                 245.2 μs   (242.1 μs .. 247.7 μs)
                         0.999 R²   (0.998 R² .. 0.999 R²)
    mean                 245.6 μs   (243.4 μs .. 251.8 μs)
    std dev              11.46 μs   (5.619 μs .. 21.69 μs)
    variance introduced by outliers: 45% (moderately inflated)

    benchmarking Large Input/Main.BinaryTree, thru list
    time                 359.7 μs   (354.4 μs .. 369.4 μs)
                         0.997 R²   (0.990 R² .. 0.999 R²)
    mean                 355.2 μs   (351.8 μs .. 363.6 μs)
    std dev              15.81 μs   (9.217 μs .. 30.55 μs)
    variance introduced by outliers: 40% (moderately inflated)

    benchmarking Large Input/Main.BinaryTree, explicit allocation
    time                 9.864 ms   (9.668 ms .. 10.10 ms)
                         0.996 R²   (0.992 R² .. 0.999 R²)
    mean                 9.738 ms   (9.603 ms .. 9.853 ms)
    std dev              342.0 μs   (249.1 μs .. 453.1 μs)
    variance introduced by outliers: 12% (moderately inflated)

    benchmarking Large Input/Main.BinaryTreeWithSize
    time                 105.9 μs   (105.0 μs .. 107.1 μs)
                         0.999 R²   (0.997 R² .. 1.000 R²)
    mean                 105.4 μs   (104.8 μs .. 106.5 μs)
    std dev              3.101 μs   (1.980 μs .. 4.735 μs)
    variance introduced by outliers: 27% (moderately inflated)

    benchmarking Large Input/FastBuilder
    time                 379.1 μs   (371.6 μs .. 391.9 μs)
                         0.993 R²   (0.986 R² .. 0.998 R²)
    mean                 379.8 μs   (374.6 μs .. 386.6 μs)
    std dev              22.80 μs   (13.63 μs .. 31.56 μs)
    variance introduced by outliers: 55% (severely inflated)

    benchmarking Large Input/Main.ListT
    time                 99.81 ms   (96.83 ms .. 104.3 ms)
                         0.998 R²   (0.995 R² .. 1.000 R²)
    mean                 99.98 ms   (99.07 ms .. 101.4 ms)
    std dev              1.734 ms   (1.173 ms .. 2.397 ms)

    benchmarking Large Input/List
    time                 48.57 ms   (46.84 ms .. 49.90 ms)
                         0.997 R²   (0.995 R² .. 0.999 R²)
    mean                 47.77 ms   (46.96 ms .. 48.49 ms)
    std dev              1.440 ms   (1.090 ms .. 2.083 ms)

    benchmarking Large Input/Data.ByteString.Builder
    time                 291.8 μs   (288.9 μs .. 294.7 μs)
                         0.999 R²   (0.996 R² .. 0.999 R²)
    mean                 288.1 μs   (285.0 μs .. 292.6 μs)
    std dev              11.79 μs   (8.794 μs .. 17.42 μs)
    variance introduced by outliers: 37% (moderately inflated)

    benchmarking Large Input/Data.ByteString
    time                 2.422 ms   (2.352 ms .. 2.482 ms)
                         0.994 R²   (0.990 R² .. 0.996 R²)
    mean                 2.496 ms   (2.456 ms .. 2.549 ms)
    std dev              161.2 μs   (134.3 μs .. 203.4 μs)
    variance introduced by outliers: 46% (moderately inflated)
