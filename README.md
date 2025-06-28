For checking if a function ends and dont worry about memory leaks since
FuncConnect will automatically clean up connections after the function is done.

Example script:

local FuncConnect = require(Path-To-FuncConnect)

local function Test(String : string)
    print("HI! " .. String)

    return "Tested!"
end

local newConnection = FuncConnect.new(Test, "WORLD!")

newConnection.Ended:Connect(function(result)
    print(result)
end)

-> Output: "HI! WORLD!"
-> Output: "Tested!"
