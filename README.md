# test
="[" & LEFT([MyString], IF(ISERROR(FIND(",", [MyString])), LEN([MyString]), FIND(",", [MyString]) - 1)) & """,""" & IF(ISERROR(FIND(",", [MyString], FIND(",", [MyString]) + 1)), MID([MyString], FIND(",", [MyString]) + 1, LEN([MyString])), MID([MyString], FIND(",", [MyString]) + 1, FIND(",", [MyString], FIND(",", [MyString]) + 1) - FIND(",", [MyString]) - 1)) & """,""" & IF(ISERROR(FIND(",", [MyString], FIND(",", [MyString]) + 1)), "", RIGHT([MyString], LEN([MyString]) - FIND(",", [MyString], FIND(",", [MyString]) + 1))) & "]"

=CONCATENATE("[", IF(ISNUMBER(FIND(",", [YourColumnName])), MID([YourColumnName], 1, FIND(",", [YourColumnName]) - 1) & """,""", ""), MID([YourColumnName], FIND(",", [YourColumnName]) + 1, LEN([YourColumnName])), """]")
