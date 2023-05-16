#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

#Depending on the operating system of the host machines(s) that will build or run the containers, the image specified in the FROM statement may need to be changed.
#For more information, please see https://aka.ms/containercompat

# Dockerfile for AiRecruitingPlatform.Tests
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["AiRecruitingPlatform.Tests.csproj", "./"]
RUN dotnet restore "AiRecruitingPlatform.Tests.csproj"
COPY . .
RUN dotnet build "AiRecruitingPlatform.Tests.csproj" -c Release
RUN dotnet test --no-build -c Release --verbosity normal
