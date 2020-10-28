dotnet new sln

dotnet new classlib -n Domain
dotnet new classlib -n Application
dotnet new classlib -n Persistence
dotnet new webapi -n API

dotnet sln add Domain/ Application/ Persistence/ API/

dotnet run -p API/ #running app

dotnet ef migrations add InitialCreate -p Persistence/ -s API/ #data project  && connection string 

cd API/ && dotnet watch run

dotnet ef migrations add SeedValues -p Persistence/ -s API/ -v #detailed flag usage