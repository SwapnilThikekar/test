# test
="[" & LEFT([MyString], IF(ISERROR(FIND(",", [MyString])), LEN([MyString]), FIND(",", [MyString]) - 1)) & """,""" & IF(ISERROR(FIND(",", [MyString], FIND(",", [MyString]) + 1)), MID([MyString], FIND(",", [MyString]) + 1, LEN([MyString])), MID([MyString], FIND(",", [MyString]) + 1, FIND(",", [MyString], FIND(",", [MyString]) + 1) - FIND(",", [MyString]) - 1)) & """,""" & IF(ISERROR(FIND(",", [MyString], FIND(",", [MyString]) + 1)), "", RIGHT([MyString], LEN([MyString]) - FIND(",", [MyString], FIND(",", [MyString]) + 1))) & "]"

=CONCATENATE("[", IF(ISNUMBER(FIND(",", [YourColumnName])), MID([YourColumnName], 1, FIND(",", [YourColumnName]) - 1) & """,""", ""), MID([YourColumnName], FIND(",", [YourColumnName]) + 1, LEN([YourColumnName])), """]")


="[""" & LEFT([YourColumnName], FIND(",", [YourColumnName]) - 1) & """,""" & MID([YourColumnName], FIND(",", [YourColumnName]) + 1, FIND(",", [YourColumnName], FIND(",", [YourColumnName]) + 1) - FIND(",", [YourColumnName]) - 1) & """,""" & MID([YourColumnName], FIND(",", [YourColumnName], FIND(",", [YourColumnName]) + 1) + 1, FIND(",", [YourColumnName], FIND(",", [YourColumnName], FIND(",", [YourColumnName]) + 1) + 1) - FIND(",", [YourColumnName], FIND(",", [YourColumnName]) + 1) - 1) & """,""" & MID([YourColumnName], FIND(",", [YourColumnName], FIND(",", [YourColumnName], FIND(",", [YourColumnName]) + 1) + 1) + 1, FIND(",", [YourColumnName], FIND(",", [YourColumnName], FIND(",", [YourColumnName], FIND(",", [YourColumnName]) + 1) + 1) + 1) - FIND(",", [YourColumnName], FIND(",", [YourColumnName], FIND(",", [YourColumnName]) + 1) + 1) - 1) & """,""" & MID([YourColumnName], FIND(",", [YourColumnName], FIND(",", [YourColumnName], FIND(",", [YourColumnName], FIND(",", [YourColumnName]) + 1) + 1) + 1) + 1, LEN([YourColumnName])) & """]"

=CONCATENATE("[", IF(ISNUMBER(FIND(",", [YourColumnName])), MID([YourColumnName], 1, FIND(",", [YourColumnName]) - 1) & """,""", ""), MID([YourColumnName], FIND(",", [YourColumnName]) + 1, IF(ISNUMBER(FIND(",", MID([YourColumnName], FIND(",", [YourColumnName]) + 1, LEN([YourColumnName])))), FIND(",", MID([YourColumnName], FIND(",", [YourColumnName]) + 1, LEN([YourColumnName]))) - 1, LEN(MID([YourColumnName], FIND(",", [YourColumnName]) + 1, LEN([YourColumnName])))))) & """]"

=IF(ISNUMBER(FIND("swap", [YourColumnName])), CONCATENATE(LEFT([YourColumnName], FIND("swap", [YourColumnName]) - 1), """", MID([YourColumnName], FIND("swap", [YourColumnName]) + LEN("swap"), LEN([YourColumnName]))), [YourColumnName])
