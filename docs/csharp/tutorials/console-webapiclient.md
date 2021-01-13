---
title: .NET Core를 사용하여 REST 클라이언트 만들기
description: 이 자습서에서는 .NET Core 및 C# 언어의 몇 가지 기능을 설명합니다.
ms.date: 01/09/2020
ms.assetid: 51033ce2-7a53-4cdd-966d-9da15c8204d2
ms.openlocfilehash: a8490efbc954ca585a2a0fa9d571191095a4b24c
ms.sourcegitcommit: 5d9cee27d9ffe8f5670e5f663434511e81b8ac38
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2021
ms.locfileid: "98024979"
---
# <a name="rest-client"></a><span data-ttu-id="3fee3-103">REST 클라이언트</span><span class="sxs-lookup"><span data-stu-id="3fee3-103">REST client</span></span>

<span data-ttu-id="3fee3-104">이 자습서에서는 .NET Core 및 C# 언어의 다양한 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-104">This tutorial teaches you a number of features in .NET Core and the C# language.</span></span> <span data-ttu-id="3fee3-105">다음에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-105">You'll learn:</span></span>

* <span data-ttu-id="3fee3-106">.NET Core CLI의 기본 사항</span><span class="sxs-lookup"><span data-stu-id="3fee3-106">The basics of the .NET Core CLI.</span></span>
* <span data-ttu-id="3fee3-107">C# 언어 기능의 개요</span><span class="sxs-lookup"><span data-stu-id="3fee3-107">An overview of C# Language features.</span></span>
* <span data-ttu-id="3fee3-108">NuGet으로 종속성 관리</span><span class="sxs-lookup"><span data-stu-id="3fee3-108">Managing dependencies with NuGet</span></span>
* <span data-ttu-id="3fee3-109">HTTP 통신</span><span class="sxs-lookup"><span data-stu-id="3fee3-109">HTTP Communications</span></span>
* <span data-ttu-id="3fee3-110">JSON 정보 처리</span><span class="sxs-lookup"><span data-stu-id="3fee3-110">Processing JSON information</span></span>
* <span data-ttu-id="3fee3-111">특성을 사용하여 구성 관리</span><span class="sxs-lookup"><span data-stu-id="3fee3-111">Managing configuration with Attributes.</span></span>

<span data-ttu-id="3fee3-112">GitHub에서 REST 서비스에 HTTP 요청을 실행하는 애플리케이션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-112">You'll build an application that issues HTTP Requests to a REST service on GitHub.</span></span> <span data-ttu-id="3fee3-113">JSON 형식의 정보를 읽은 후 해당 JSON 패킷을 C# 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-113">You'll read information in JSON format, and convert that JSON packet into C# objects.</span></span> <span data-ttu-id="3fee3-114">마지막으로 C# 개체를 사용하는 방법을 배웁니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-114">Finally, you'll see how to work with C# objects.</span></span>

<span data-ttu-id="3fee3-115">이 자습서에는 많은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-115">There are many features in this tutorial.</span></span> <span data-ttu-id="3fee3-116">하나씩 빌드해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-116">Let's build them one by one.</span></span>

<span data-ttu-id="3fee3-117">이 문서의 [최종 샘플](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)을 따르려는 경우 해당 샘플을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-117">If you prefer to follow along with the [final sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient) for this article, you can download it.</span></span> <span data-ttu-id="3fee3-118">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#view-and-download-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fee3-118">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#view-and-download-samples).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3fee3-119">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fee3-119">Prerequisites</span></span>

<span data-ttu-id="3fee3-120">.NET Core를 실행하려면 머신을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-120">You'll need to set up your machine to run .NET core.</span></span> <span data-ttu-id="3fee3-121">[.NET Core 다운로드](https://dotnet.microsoft.com/download) 페이지에서 설치 지침을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-121">You can find the installation instructions on the [.NET Core Downloads](https://dotnet.microsoft.com/download) page.</span></span> <span data-ttu-id="3fee3-122">Windows, Linux, macOS에서나 Docker 컨테이너에서 이 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-122">You can run this application on Windows, Linux, or macOS, or in a Docker container.</span></span>
<span data-ttu-id="3fee3-123">선호하는 코드 편집기를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-123">You'll need to install your favorite code editor.</span></span> <span data-ttu-id="3fee3-124">아래 설명에서는 오픈 소스 플랫폼 간 편집기인 [Visual Studio Code](https://code.visualstudio.com/)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-124">The descriptions below use [Visual Studio Code](https://code.visualstudio.com/), which is an open source, cross platform editor.</span></span> <span data-ttu-id="3fee3-125">그러나 익숙한 어떤 도구도 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-125">However, you can use whatever tools you are comfortable with.</span></span>

## <a name="create-the-application"></a><span data-ttu-id="3fee3-126">애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="3fee3-126">Create the Application</span></span>

<span data-ttu-id="3fee3-127">첫 번째 단계에서는 새 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-127">The first step is to create a new application.</span></span> <span data-ttu-id="3fee3-128">명령 프롬프트를 열고 애플리케이션에 대한 새 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-128">Open a command prompt and create a new directory for your application.</span></span> <span data-ttu-id="3fee3-129">해당 디렉터리를 현재 디렉터리로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-129">Make that the current directory.</span></span> <span data-ttu-id="3fee3-130">콘솔 창에 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-130">Enter the following command in a console window:</span></span>

```dotnetcli
dotnet new console --name WebAPIClient
```

<span data-ttu-id="3fee3-131">이렇게 하면 기본 "Hello World" 애플리케이션에 대한 시작 파일이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-131">This creates the starter files for a basic "Hello World" application.</span></span> <span data-ttu-id="3fee3-132">프로젝트 이름은 "WebAPIClient"입니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-132">The project name is "WebAPIClient".</span></span> <span data-ttu-id="3fee3-133">새 프로젝트이므로 어떤 종속성도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-133">As this is a new project, none of the dependencies are in place.</span></span> <span data-ttu-id="3fee3-134">첫 번째 실행에서는 .NET Core 프레임워크를 다운로드하고, 개발 인증서를 설치하며, NuGet 패키지 관리자를 실행하여 누락된 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-134">The first run will download the .NET Core framework, install a development certificate, and run the NuGet package manager to restore missing dependencies.</span></span>

<span data-ttu-id="3fee3-135">수정하기 전에 “WebAPIClient” 디렉터리에 `cd`하고 명령 프롬프트에서 `dotnet run`([참고 참조](#dotnet-restore-note))를 입력하여 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-135">Before you start making modifications, `cd` into the "WebAPIClient" directory and type `dotnet run` ([see note](#dotnet-restore-note)) at the command prompt to run your application.</span></span> <span data-ttu-id="3fee3-136">환경에 누락된 종속성이 있으면 `dotnet run`이 자동으로 `dotnet restore`를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-136">`dotnet run` automatically performs `dotnet restore` if your environment is missing dependencies.</span></span> <span data-ttu-id="3fee3-137">애플리케이션을 다시 빌드해야 하면 `dotnet build`도 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-137">It also performs `dotnet build` if your application needs to be rebuilt.</span></span>
<span data-ttu-id="3fee3-138">최초 설치 후에는 프로젝트에 해당할 때만 `dotnet restore` 또는 `dotnet build`를 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-138">After your initial setup, you will only need to run `dotnet restore` or `dotnet build` when it makes sense for your project.</span></span>

## <a name="adding-new-dependencies"></a><span data-ttu-id="3fee3-139">새 종속성 추가</span><span class="sxs-lookup"><span data-stu-id="3fee3-139">Adding New Dependencies</span></span>

<span data-ttu-id="3fee3-140">.NET Core의 주요 디자인 목표 중 하나는 .NET 설치의 크기를 최소화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-140">One of the key design goals for .NET Core is to minimize the size of the .NET installation.</span></span> <span data-ttu-id="3fee3-141">애플리케이션에 일부 기능을 위해 추가 라이브러리가 필요한 경우 C# 프로젝트(\*.csproj) 파일에 해당 종속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-141">If an application needs additional libraries for some of its features, you add those dependencies into your C# project (\*.csproj) file.</span></span> <span data-ttu-id="3fee3-142">현재 예제에서는 애플리케이션이 JSON 응답을 처리할 수 있도록 `System.Runtime.Serialization.Json` 패키지를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-142">For our example, you'll need to add the `System.Runtime.Serialization.Json` package, so your application can process JSON responses.</span></span>

<span data-ttu-id="3fee3-143">이 애플리케이션에는 `System.Runtime.Serialization.Json` 패키지가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-143">You'll need the `System.Runtime.Serialization.Json` package for this application.</span></span> <span data-ttu-id="3fee3-144">다음 [.NET CLI](../../core/tools/dotnet-add-package.md) 명령을 실행하여 패키지를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-144">Add it to your project by running the following [.NET CLI](../../core/tools/dotnet-add-package.md) command:</span></span>

```dotnetcli
dotnet add package System.Text.Json
```

## <a name="making-web-requests"></a><span data-ttu-id="3fee3-145">웹 요청 수행</span><span class="sxs-lookup"><span data-stu-id="3fee3-145">Making Web Requests</span></span>

<span data-ttu-id="3fee3-146">이제 웹에서 데이터 검색을 시작할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-146">Now you're ready to start retrieving data from the web.</span></span> <span data-ttu-id="3fee3-147">이 애플리케이션에서는 [GitHub API](https://developer.github.com/v3/)에서 정보를 읽게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-147">In this application, you'll read information from the [GitHub API](https://developer.github.com/v3/).</span></span> <span data-ttu-id="3fee3-148">[.NET Foundation](https://www.dotnetfoundation.org/) 상위 항목 아래에서 프로젝트에 대한 정보를 읽어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-148">Let's read information about the projects under the [.NET Foundation](https://www.dotnetfoundation.org/) umbrella.</span></span> <span data-ttu-id="3fee3-149">먼저 GitHub API에 대해 요청을 수행하여 프로젝트에 대한 정보를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-149">You'll start by making the request to the GitHub API to retrieve information on the projects.</span></span> <span data-ttu-id="3fee3-150">사용할 엔드포인트는 <https://api.github.com/orgs/dotnet/repos>입니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-150">The endpoint you'll use is: <https://api.github.com/orgs/dotnet/repos>.</span></span> <span data-ttu-id="3fee3-151">이러한 프로젝트에 대해 모든 정보를 검색하려고 하므로 HTTP GET 요청을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-151">You want to retrieve all the information about these projects, so you'll use an HTTP GET request.</span></span>
<span data-ttu-id="3fee3-152">브라우저도 HTTP GET 요청을 사용하므로 해당 URL을 브라우저에 붙여 넣어 수신되고 처리 중인 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-152">Your browser also uses HTTP GET requests, so you can paste that URL into your browser to see what information you'll be receiving and processing.</span></span>

<span data-ttu-id="3fee3-153"><xref:System.Net.Http.HttpClient> 클래스를 사용하여 웹 요청을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-153">You use the <xref:System.Net.Http.HttpClient> class to make web requests.</span></span> <span data-ttu-id="3fee3-154">모든 최신 .NET API와 마찬가지로 <xref:System.Net.Http.HttpClient> 는 장기 실행되는 API에 대해 비동기 메서드만 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-154">Like all modern .NET APIs, <xref:System.Net.Http.HttpClient> supports only async methods for its long-running APIs.</span></span>
<span data-ttu-id="3fee3-155">먼저 비동기 메서드를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-155">Start by making an async method.</span></span> <span data-ttu-id="3fee3-156">애플리케이션의 기능을 빌드할 때 구현을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-156">You'll fill in the implementation as you build the functionality of the application.</span></span> <span data-ttu-id="3fee3-157">먼저 프로젝트 디렉터리에서 `program.cs` 파일을 열고 `Program` 클래스에 다음 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-157">Start by opening the `program.cs` file in your project directory and adding the following method to the `Program` class:</span></span>

```csharp
private static async Task ProcessRepositories()
{
}
```

<span data-ttu-id="3fee3-158">C# 컴파일러에서 <xref:System.Threading.Tasks.Task> 형식을 인식하도록 `using` 지시문을 `Main` 메서드 맨 위에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-158">You'll need to add a `using` directive at the top of your `Main` method so that the C# compiler recognizes the <xref:System.Threading.Tasks.Task> type:</span></span>

```csharp
using System.Threading.Tasks;
```

<span data-ttu-id="3fee3-159">이때 프로젝트를 빌드하면 이 메서드에는 `await` 연산자가 없어서 동기적으로 실행되므로 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-159">If you build your project at this point, you'll get a warning generated for this method, because it does not contain any `await` operators and will run synchronously.</span></span> <span data-ttu-id="3fee3-160">지금은 이 경고를 무시하세요. 메서드를 입력할 때 `await` 연산자를 추가할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-160">Ignore that for now; you'll add `await` operators as you fill in the method.</span></span>

<span data-ttu-id="3fee3-161">다음으로 `Main` 메서드를 업데이트하여 `ProcessRepositories` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-161">Next, update the `Main` method to call the `ProcessRepositories` method.</span></span> <span data-ttu-id="3fee3-162">`ProcessRepositories` 메서드는 작업을 반환합니다. 이 작업이 완료되기 전에 프로그램을 종료하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-162">The `ProcessRepositories` method returns a task, and you shouldn't exit the program before that task finishes.</span></span> <span data-ttu-id="3fee3-163">따라서 `Main`의 서명을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-163">Therefore, you must change the signature of `Main`.</span></span> <span data-ttu-id="3fee3-164">`async` 한정자를 추가하고 반환 형식을 `Task`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-164">Add the `async` modifier, and change the return type to `Task`.</span></span> <span data-ttu-id="3fee3-165">그런 다음 메서드의 본문에서 `ProcessRepositories`에 대한 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-165">Then, in the body of the method, add a call to `ProcessRepositories`.</span></span> <span data-ttu-id="3fee3-166">해당 메서드 호출에 `await` 키워드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-166">Add the `await` keyword to that method call:</span></span>

```csharp
static async Task Main(string[] args)
{
    await ProcessRepositories();
}
```

<span data-ttu-id="3fee3-167">이제 아무 작업도 수행하지 않지만 비동기적으로는 수행하는 프로그램이 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-167">Now, you have a program that does nothing, but does it asynchronously.</span></span> <span data-ttu-id="3fee3-168">이것을 개선해보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-168">Let's improve it.</span></span>

<span data-ttu-id="3fee3-169">먼저 웹에서 데이터를 검색할 수 있는 개체가 필요합니다. 이를 위해 <xref:System.Net.Http.HttpClient>를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-169">First you need an object that is capable to retrieve data from the web; you can use a <xref:System.Net.Http.HttpClient> to do that.</span></span> <span data-ttu-id="3fee3-170">이 개체는 요청 및 응답을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-170">This object handles the request and the responses.</span></span> <span data-ttu-id="3fee3-171">*Program.cs* 파일 내의 `Program` 클래스에서 해당 형식의 단일 인스턴스를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-171">Instantiate a single instance of that type in the `Program` class inside the *Program.cs* file.</span></span>

```csharp
namespace WebAPIClient
{
    class Program
    {
        private static readonly HttpClient client = new HttpClient();

        static async Task Main(string[] args)
        {
            //...
        }
    }
}
```

<span data-ttu-id="3fee3-172">다시 `ProcessRepositories` 메서드로 돌아가 첫 번째 버전을 채워 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-172">Let's go back to the `ProcessRepositories` method and fill in a first version of it:</span></span>

```csharp
private static async Task ProcessRepositories()
{
    client.DefaultRequestHeaders.Accept.Clear();
    client.DefaultRequestHeaders.Accept.Add(
        new MediaTypeWithQualityHeaderValue("application/vnd.github.v3+json"));
    client.DefaultRequestHeaders.Add("User-Agent", ".NET Foundation Repository Reporter");

    var stringTask = client.GetStringAsync("https://api.github.com/orgs/dotnet/repos");

    var msg = await stringTask;
    Console.Write(msg);
}
```

<span data-ttu-id="3fee3-173">컴파일을 위해 파일 맨 위에 2개의 새 `using` 지시문도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-173">You'll need to also add two new `using` directives at the top of the file for this to compile:</span></span>

```csharp
using System.Net.Http;
using System.Net.Http.Headers;
```

<span data-ttu-id="3fee3-174">이 첫 번째 버전은 dotnet foundation 조직의 모든 리포지토리 목록을 읽으라는 웹 요청을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-174">This first version makes a web request to read the list of all repositories under the dotnet foundation organization.</span></span> <span data-ttu-id="3fee3-175">(.NET Foundation의 GitHub ID는 `dotnet`임) 첫 몇 줄은 이 요청에 대해 <xref:System.Net.Http.HttpClient>를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-175">(The GitHub ID for the .NET Foundation is `dotnet`.) The first few lines set up the <xref:System.Net.Http.HttpClient> for this request.</span></span> <span data-ttu-id="3fee3-176">먼저 GitHub JSON 응답을 수락하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-176">First, it is configured to accept the GitHub JSON responses.</span></span>
<span data-ttu-id="3fee3-177">이 형식은 단순히 JSON입니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-177">This format is simply JSON.</span></span> <span data-ttu-id="3fee3-178">다음 줄은 이 개체의 모든 요청에 사용자 에이전트 헤더를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-178">The next line adds a User Agent header to all requests from this object.</span></span> <span data-ttu-id="3fee3-179">이러한 두 가지 헤더는 GitHub 서버 코드에서 확인되며 GitHub에서 정보를 검색하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-179">These two headers are checked by the GitHub server code, and are necessary to retrieve information from GitHub.</span></span>

<span data-ttu-id="3fee3-180"><xref:System.Net.Http.HttpClient> 를 구성한 후에는 웹 요청을 수행하고 응답을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-180">After you've configured the <xref:System.Net.Http.HttpClient>, you make a web request and retrieve the response.</span></span> <span data-ttu-id="3fee3-181">이 첫 번째 버전에서는 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> 편의 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-181">In this first version, you use the <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)?displayProperty=nameWithType> convenience method.</span></span> <span data-ttu-id="3fee3-182">이 편의 메서드는 웹 요청을 수행하는 작업을 시작한 다음, 요청이 반환될 때 응답 스트림을 읽고 해당 스트림에서 콘텐츠를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-182">This convenience method starts a task that makes the web request, and then when the request returns, it reads the response stream and extracts the content from the stream.</span></span> <span data-ttu-id="3fee3-183">응답의 본문은 <xref:System.String> 으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-183">The body of the response is returned as a <xref:System.String>.</span></span> <span data-ttu-id="3fee3-184">작업이 완료되면 이 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-184">The string is available when the task completes.</span></span>

<span data-ttu-id="3fee3-185">이 메서드의 마지막 두 줄은 해당 작업을 대기하고 콘솔에 응답을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-185">The final two lines of this method await that task, and then print the response to the console.</span></span>
<span data-ttu-id="3fee3-186">앱을 빌드한 다음 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-186">Build the app, and run it.</span></span> <span data-ttu-id="3fee3-187">`ProcessRepositories`에는 `await` 연산자가 포함되므로 이제 빌드 경고는 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-187">The build warning is gone now, because the `ProcessRepositories` now does contain an `await` operator.</span></span> <span data-ttu-id="3fee3-188">길게 표시되는 JSON 형식 텍스트를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-188">You'll see a long display of JSON formatted text.</span></span>

## <a name="processing-the-json-result"></a><span data-ttu-id="3fee3-189">JSON 결과 처리</span><span class="sxs-lookup"><span data-stu-id="3fee3-189">Processing the JSON Result</span></span>

<span data-ttu-id="3fee3-190">지금까지 웹 서버에서 응답을 검색하고 해당 응답에 포함된 텍스트를 표시하는 코드를 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-190">At this point, you've written the code to retrieve a response from a web server, and display the text that is contained in that response.</span></span> <span data-ttu-id="3fee3-191">다음에는 JSON 응답을 C# 개체로 변환해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-191">Next, let's convert that JSON response into C# objects.</span></span>

<span data-ttu-id="3fee3-192"><xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> 클래스는 개체를 JSON으로 직렬화하고 JSON을 개체로 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-192">The <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> class serializes objects to JSON and deserializes JSON into objects.</span></span> <span data-ttu-id="3fee3-193">먼저 GitHub API에서 반환된 `repo` JSON 개체를 나타내도록 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-193">Start by defining a class to represent the `repo` JSON object returned from the GitHub API:</span></span>

```csharp
using System;

namespace WebAPIClient
{
    public class Repository
    {
        public string name { get; set; }
    }
}
```

<span data-ttu-id="3fee3-194">'repo.cs'라는 새 파일에 위 코드를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-194">Put the above code in a new file called 'repo.cs'.</span></span> <span data-ttu-id="3fee3-195">이 버전의 클래스는 JSON 데이터를 처리하는 가장 간단한 경로를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-195">This version of the class represents the simplest path to process JSON data.</span></span> <span data-ttu-id="3fee3-196">클래스 이름 및 멤버 이름은 다음 C# 규칙 대신 JSON 패킷에 사용된 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-196">The class name and the member name match the names used in the JSON packet, instead of following C# conventions.</span></span> <span data-ttu-id="3fee3-197">나중에 몇 가지 구성 특성을 제공하여 수정할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-197">You'll fix that by providing some configuration attributes later.</span></span> <span data-ttu-id="3fee3-198">이 클래스에서는 JSON serialization 및 deserialization의 또 다른 중요한 특징을 보여 줍니다. 즉, JSON 패킷의 모든 필드가 이 클래스에 속하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-198">This class demonstrates another important feature of JSON serialization and deserialization: Not all the fields in the JSON packet are part of this class.</span></span>
<span data-ttu-id="3fee3-199">JSON serializer는 사용되는 클래스 형식에 포함되지 않은 정보를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-199">The JSON serializer will ignore information that is not included in the class type being used.</span></span>
<span data-ttu-id="3fee3-200">이 특징 때문에 JSON 패킷의 필드 일부에만 작용하는 형식을 보다 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-200">This feature makes it easier to create types that work with only a subset of the fields in the JSON packet.</span></span>

<span data-ttu-id="3fee3-201">이제 형식을 만들었으므로 역직렬화를 수행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-201">Now that you've created the type, let's deserialize it.</span></span>

<span data-ttu-id="3fee3-202">다음으로, serializer를 사용하여 JSON을 C# 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-202">Next, you'll use the serializer to convert JSON into C# objects.</span></span> <span data-ttu-id="3fee3-203">`ProcessRepositories` 메서드의 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> 호출을 다음 줄로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-203">Replace the call to <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> in your `ProcessRepositories` method with the following lines:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
```

<span data-ttu-id="3fee3-204">새 네임 스페이스를 사용하고 있으므로 파일의 맨 위에도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-204">You're using new namespaces, so you'll need to add it at the top of the file as well:</span></span>

```csharp
using System.Collections.Generic;
using System.Text.Json;
```

<span data-ttu-id="3fee3-205">현재 <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)> 대신 <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)>를 사용하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-205">Notice that you're now using <xref:System.Net.Http.HttpClient.GetStreamAsync(System.String)> instead of <xref:System.Net.Http.HttpClient.GetStringAsync(System.String)>.</span></span> <span data-ttu-id="3fee3-206">serializer는 해당 소스로 문자열 대신 스트림을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-206">The serializer uses a stream instead of a string as its source.</span></span> <span data-ttu-id="3fee3-207">앞의 코드 조각 두 번째 줄에서 사용되는 C# 언어의 몇 가지 기능에 대해 설명해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-207">Let's explain a couple features of the C# language that are being used in the second line of the preceding code snippet.</span></span> <span data-ttu-id="3fee3-208"><xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>에 대한 첫 번째 인수는 `await` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-208">The first argument to <xref:System.Text.Json.JsonSerializer.DeserializeAsync%60%601(System.IO.Stream,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType> is an `await` expression.</span></span> <span data-ttu-id="3fee3-209">(다른 두 매개 변수는 선택 사항이며 코드 조각에서 생략됩니다.) 지금까지는 대입문의 일부로만 볼 수 있었지만 Await 식은 코드의 거의 모든 위치에 나올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-209">(The other two parameters are optional and are omitted in the code snippet.) Await expressions can appear almost anywhere in your code, even though up to now, you've only seen them as part of an assignment statement.</span></span> <span data-ttu-id="3fee3-210">`Deserialize` 메서드는 *제네릭* 입니다. 즉, JSON 텍스트에서 만들어야 하는 개체 종류에 대한 형식 인수를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-210">The `Deserialize` method is *generic*, which means you must supply type arguments for what kind of objects should be created from the JSON text.</span></span> <span data-ttu-id="3fee3-211">이 예제에서는 다른 제네릭 개체 <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>인 `List<Repository>`로 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-211">In this example, you're deserializing to a `List<Repository>`, which is another generic object, the <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3fee3-212">`List<>` 클래스는 개체의 컬렉션을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-212">The `List<>` class stores a collection of objects.</span></span> <span data-ttu-id="3fee3-213">형식 인수는 `List<>`에 저장된 개체의 형식을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-213">The type argument declares the type of objects stored in the `List<>`.</span></span> <span data-ttu-id="3fee3-214">JSON 텍스트는 리포지토리 개체의 컬렉션을 나타내므로 형식 인수는 `Repository`입니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-214">The JSON text represents a collection of repo objects, so the type argument is `Repository`.</span></span>

<span data-ttu-id="3fee3-215">이 섹션이 거의 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-215">You're almost done with this section.</span></span> <span data-ttu-id="3fee3-216">JSON을 C# 개체로 변환했으므로 각 리포지토리의 이름을 표시해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-216">Now that you've converted the JSON to C# objects, let's display the name of each repository.</span></span> <span data-ttu-id="3fee3-217">다음 줄을</span><span class="sxs-lookup"><span data-stu-id="3fee3-217">Replace the lines that read:</span></span>

```csharp
var msg = await stringTask;   //**Deleted this
Console.Write(msg);
```

<span data-ttu-id="3fee3-218">다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-218">with the following:</span></span>

```csharp
foreach (var repo in repositories)
    Console.WriteLine(repo.name);
```

<span data-ttu-id="3fee3-219">애플리케이션을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-219">Compile and run the application.</span></span> <span data-ttu-id="3fee3-220">.NET Foundation에 포함된 리포지토리의 이름이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-220">It will print the names of the repositories that are part of the .NET Foundation.</span></span>

## <a name="controlling-serialization"></a><span data-ttu-id="3fee3-221">serialization 제어</span><span class="sxs-lookup"><span data-stu-id="3fee3-221">Controlling Serialization</span></span>

<span data-ttu-id="3fee3-222">더 많은 기능을 추가하기 전에 `[JsonPropertyName]` 특성을 사용하여 `name` 속성을 다뤄 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-222">Before you add more features, let's address the `name` property by using the `[JsonPropertyName]` attribute.</span></span> <span data-ttu-id="3fee3-223">repo.cs에서 `name` 필드의 선언을 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-223">Make the following changes to the declaration of the `name` field in repo.cs:</span></span>

```csharp
[JsonPropertyName("name")]
public string Name { get; set; }
```

<span data-ttu-id="3fee3-224">`[JsonPropertyName]` 특성을 사용하려면 `using` 지시문에 <xref:System.Text.Json.Serialization> 네임스페이스를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-224">To use `[JsonPropertyName]` attribute, you will need to add the <xref:System.Text.Json.Serialization> namespace to the `using` directives:</span></span>

```csharp
using System.Text.Json.Serialization;
```

<span data-ttu-id="3fee3-225">이렇게 변경할 경우 program.cs에서 각 리포지토리의 이름을 쓰는 코드를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-225">This change means you need to change the code that writes the name of each repository in program.cs:</span></span>

```csharp
Console.WriteLine(repo.Name);
```

<span data-ttu-id="3fee3-226">`dotnet run`을 실행하여 매핑이 올바르게 수행되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-226">Execute `dotnet run` to make sure you've got the mappings correct.</span></span> <span data-ttu-id="3fee3-227">이전과 동일한 출력이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-227">You should see the same output as before.</span></span>

<span data-ttu-id="3fee3-228">새로운 기능을 추가하기 전에 한 가지 더 변경해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-228">Let's make one more change before adding new features.</span></span> <span data-ttu-id="3fee3-229">`ProcessRepositories` 메서드는 비동기 작업을 수행하고 리포지토리 컬렉션을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-229">The `ProcessRepositories` method can do the async work and return a collection of the repositories.</span></span> <span data-ttu-id="3fee3-230">이 메서드에서 `List<Repository>`로 돌아가 정보를 쓰는 코드를 `Main` 메서드로 이동해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-230">Let's return the `List<Repository>` from that method, and move the code that writes the information into the `Main` method.</span></span>

<span data-ttu-id="3fee3-231">`ProcessRepositories`의 시그니처를 변경하여 `Repository` 개체의 목록을 해당 결과로 표시하는 작업을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-231">Change the signature of `ProcessRepositories` to return a task whose result is a list of `Repository` objects:</span></span>

```csharp
private static async Task<List<Repository>> ProcessRepositories()
```

<span data-ttu-id="3fee3-232">다음에는 JSON 응답을 처리한 후 리포지토리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-232">Then, just return the repositories after processing the JSON response:</span></span>

```csharp
var streamTask = client.GetStreamAsync("https://api.github.com/orgs/dotnet/repos");
var repositories = await JsonSerializer.DeserializeAsync<List<Repository>>(await streamTask);
return repositories;
```

<span data-ttu-id="3fee3-233">이 개체를 `async`로 표시했으므로 컴파일러는 해당 반환에 대한 `Task<T>` 개체를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-233">The compiler generates the `Task<T>` object for the return because you've marked this method as `async`.</span></span>
<span data-ttu-id="3fee3-234">그런 다음 해당 결과를 캡처하고 각 리포지토리 이름을 콘솔에 쓰도록 `Main` 메서드를 수정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-234">Then, let's modify the `Main` method so that it captures those results and writes each repository name to the console.</span></span> <span data-ttu-id="3fee3-235">`Main` 메서드는 이제 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-235">Your `Main` method now looks like this:</span></span>

```csharp
public static async Task Main(string[] args)
{
    var repositories = await ProcessRepositories();

    foreach (var repo in repositories)
        Console.WriteLine(repo.Name);
}
```

## <a name="reading-more-information"></a><span data-ttu-id="3fee3-236">추가 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="3fee3-236">Reading More Information</span></span>

<span data-ttu-id="3fee3-237">GitHub API에서 전송되는 JSON 패킷에 있는 속성을 몇 가지 더 처리하는 것으로 마무리해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-237">Let's finish this by processing a few more of the properties in the JSON packet that gets sent from the GitHub API.</span></span> <span data-ttu-id="3fee3-238">모든 기능을 알 수는 없겠지만 일부 속성을 추가하면 C# 언어의 몇 가지 기능이 추가로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-238">You won't want to grab everything, but adding a few properties will demonstrate a few more features of the C# language.</span></span>

<span data-ttu-id="3fee3-239">먼저 `Repository` 클래스 정의에 몇 가지 간단한 형식을 더 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-239">Let's start by adding a few more simple types to the `Repository` class definition.</span></span> <span data-ttu-id="3fee3-240">해당 클래스에 다음 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-240">Add these properties to that class:</span></span>

```csharp
[JsonPropertyName("description")]
public string Description { get; set; }

[JsonPropertyName("html_url")]
public Uri GitHubHomeUrl { get; set; }

[JsonPropertyName("homepage")]
public Uri Homepage { get; set; }

[JsonPropertyName("watchers")]
public int Watchers { get; set; }
```

<span data-ttu-id="3fee3-241">이러한 속성은 기본적으로 문자열 형식(JSON 패킷에 포함된 형식)을 대상 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-241">These properties have built-in conversions from the string type (which is what the JSON packets contain) to the target type.</span></span> <span data-ttu-id="3fee3-242"><xref:System.Uri> 형식은 생소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-242">The <xref:System.Uri> type may be new to you.</span></span> <span data-ttu-id="3fee3-243">이 형식은 URI 또는 이 경우에는 URL을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-243">It represents a URI, or in this case, a URL.</span></span> <span data-ttu-id="3fee3-244">`Uri` 및 `int` 형식의 경우 JSON 패킷에 대상 형식으로 변환되지 않는 데이터가 포함되어 있으면 serialization 작업은 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-244">In the case of the `Uri` and `int` types, if the JSON packet contains data that does not convert to the target type, the serialization action will throw an exception.</span></span>

<span data-ttu-id="3fee3-245">이러한 데이터를 추가한 경우에는 해당 요소를 표시하도록 `Main` 메서드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-245">Once you've added these, update the `Main` method to display those elements:</span></span>

```csharp
foreach (var repo in repositories)
{
    Console.WriteLine(repo.Name);
    Console.WriteLine(repo.Description);
    Console.WriteLine(repo.GitHubHomeUrl);
    Console.WriteLine(repo.Homepage);
    Console.WriteLine(repo.Watchers);
    Console.WriteLine();
}
```

<span data-ttu-id="3fee3-246">마지막 단계로, 최종 밀어넣기 작업을 위한 정보를 추가해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-246">As a final step, let's add the information for the last push operation.</span></span> <span data-ttu-id="3fee3-247">이 정보는 JSON 응답에서 다음 방식으로 형식이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-247">This information is formatted in this fashion in the JSON response:</span></span>

```json
2016-02-08T21:27:00Z
```

<span data-ttu-id="3fee3-248">해당 형식은 UTC(협정 세계시)이므로 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind.Utc>인 <xref:System.DateTime> 값을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-248">That format is in Coordinated Universal Time (UTC) so you'll get a <xref:System.DateTime> value whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Utc>.</span></span> <span data-ttu-id="3fee3-249">표준 시간대로 표시되는 날짜를 선호하는 경우 사용자 지정 변환 메서드를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-249">If you prefer a date represented in your time zone, you'll need to write a custom conversion method.</span></span> <span data-ttu-id="3fee3-250">먼저 `Repository` 클래스에서 날짜 및 시간을 UTC로 표현하는 `public` 속성을 정의하고 현지 시간으로 변환된 날짜를 반환하는 `LastPush` `readonly` 속성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-250">First, define a `public` property that will hold the UTC representation of the date and time in your `Repository` class and a `LastPush` `readonly` property that returns the date converted to local time:</span></span>

```csharp
[JsonPropertyName("pushed_at")]
public DateTime LastPushUtc { get; set; }

public DateTime LastPush => LastPushUtc.ToLocalTime();
```

<span data-ttu-id="3fee3-251">방금 정의한 새 구문을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-251">Let's go over the new constructs we just defined.</span></span> <span data-ttu-id="3fee3-252">`LastPush` 속성은 `get` 접근자에 대한 *식 본문 멤버* 를 사용하여 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-252">The `LastPush` property is defined using an *expression-bodied member* for the `get` accessor.</span></span> <span data-ttu-id="3fee3-253">`set` 접근자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-253">There is no `set` accessor.</span></span> <span data-ttu-id="3fee3-254">`set` 접근자를 생략하는 것이 바로 C#에서 *읽기 전용* 속성을 정의하는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-254">Omitting the `set` accessor is how you define a *read-only* property in C#.</span></span> <span data-ttu-id="3fee3-255">(C#에서 *쓰기 전용* 속성을 만들 수 있지만 해당 값은 제한됩니다.)</span><span class="sxs-lookup"><span data-stu-id="3fee3-255">(Yes, you can create *write-only* properties in C#, but their value is limited.)</span></span>

<span data-ttu-id="3fee3-256">마지막으로 콘솔에 output 문을 하나 더 추가하면 이 앱을 빌드하고 다시 실행할 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-256">Finally, add one more output statement in the console, and you're ready to build and run this app again:</span></span>

```csharp
Console.WriteLine(repo.LastPush);
```

<span data-ttu-id="3fee3-257">이제 해당 버전이 [완성된 샘플](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient)과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-257">Your version should now match the [finished sample](https://github.com/dotnet/samples/tree/master/csharp/getting-started/console-webapiclient).</span></span>

## <a name="conclusion"></a><span data-ttu-id="3fee3-258">결론</span><span class="sxs-lookup"><span data-stu-id="3fee3-258">Conclusion</span></span>

<span data-ttu-id="3fee3-259">이 자습서에서는 웹 요청을 수행하고, 결과를 구문 분석하고, 해당 결과의 속성을 표시하는 방법을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-259">This tutorial showed you how to make web requests, parse the result, and display properties of those results.</span></span> <span data-ttu-id="3fee3-260">또한 프로젝트에 종속성으로 새 패키지를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-260">You've also added new packages as dependencies in your project.</span></span> <span data-ttu-id="3fee3-261">개체 지향 기술을 지원하는 C# 언어의 일부 기능을 확인했습니다.</span><span class="sxs-lookup"><span data-stu-id="3fee3-261">You've seen some of the features of the C# language that support object-oriented techniques.</span></span>

<a name="dotnet-restore-note"></a>

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
