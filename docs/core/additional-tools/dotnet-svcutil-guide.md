---
title: WCF svcutil 도구 개요
description: .NET Framework 프로젝트용 WCF svcutil 도구와 유사하게, .NET Core 및 ASP.NET Core 프로젝트 기능을 추가하는 Microsoft WCF dotnet-svcutil 도구에 대한 개요입니다.
author: mlacouture
ms.date: 02/22/2019
ms.openlocfilehash: 0607c73935f319f2cc0d8d9f92d96a4c71c54edf
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920943"
---
# <a name="wcf-dotnet-svcutil-tool-for-net-core"></a><span data-ttu-id="1c6b0-103">.NET Core용 WCF dotnet-svcutil 도구</span><span class="sxs-lookup"><span data-stu-id="1c6b0-103">WCF dotnet-svcutil tool for .NET Core</span></span>

<span data-ttu-id="1c6b0-104">WCF(Windows Communication Foundation) **dotnet-svcutil** 도구는 네트워크 위치의 웹 서비스 또는 WSDL 파일에서 메타데이터를 검색하고, 해당 웹 서비스 작업에 액세스하는 클라이언트 프록시 메서드가 포함된 WCF 클래스를 생성하는 .NET 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-104">The Windows Communication Foundation (WCF) **dotnet-svcutil** tool is a .NET tool that retrieves metadata from a web service on a network location or from a WSDL file, and generates a WCF class containing client proxy methods that access the web service operations.</span></span>

<span data-ttu-id="1c6b0-105">.NET Framework 프로젝트용 [**서비스 모델 메타데이터 - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구와 비슷하게, **dotnet-svcutil**은 .NET Core 및 .NET Standard 프로젝트와 호환되는 웹 서비스 참조를 생성하기 위한 명령줄 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-105">Similar to the [**Service Model Metadata - svcutil**](../../framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool for .NET Framework projects, the **dotnet-svcutil** is a command-line tool for generating a web service reference compatible with .NET Core and .NET Standard projects.</span></span>

<span data-ttu-id="1c6b0-106">**dotnet-svcutil** 도구는 Visual Studio 2017 버전 15.5에서 처음 제공된 [**WCF Web Service Reference Provider 도구 사용**](wcf-web-service-reference-guide.md) Visual Studio 연결된 서비스 공급자의 대체 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-106">The **dotnet-svcutil** tool is an alternative option to the [**WCF Web Service Reference**](wcf-web-service-reference-guide.md) Visual Studio connected service provider that first shipped with Visual Studio 2017 version 15.5.</span></span> <span data-ttu-id="1c6b0-107">.NET 도구인 **dotnet-svcutil** 도구는 Linux, macOS, Windows와 같은 여러 플랫폼에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-107">The **dotnet-svcutil** tool as a .NET tool, is available cross-platform on Linux, macOS, and Windows.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c6b0-108">신뢰할 수 있는 원본의 서비스만 참조해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-108">You should only reference services from a trusted source.</span></span> <span data-ttu-id="1c6b0-109">신뢰할 수 없는 원본에서 참조를 추가하면 보안이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-109">Adding references from an untrusted source may compromise security.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1c6b0-110">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c6b0-110">Prerequisites</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[<span data-ttu-id="1c6b0-111">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="1c6b0-111">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

- <span data-ttu-id="1c6b0-112">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) 이상 버전</span><span class="sxs-lookup"><span data-stu-id="1c6b0-112">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later versions</span></span>
- <span data-ttu-id="1c6b0-113">선호하는 코드 편집기</span><span class="sxs-lookup"><span data-stu-id="1c6b0-113">Your favorite code editor</span></span>

# <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[<span data-ttu-id="1c6b0-114">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="1c6b0-114">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

- <span data-ttu-id="1c6b0-115">[.NET Core 1.0.4 SDK](https://dotnet.microsoft.com/download) 이상 버전</span><span class="sxs-lookup"><span data-stu-id="1c6b0-115">[.NET Core 1.0.4 SDK](https://dotnet.microsoft.com/download) or later versions</span></span>
- <span data-ttu-id="1c6b0-116">선호하는 코드 편집기</span><span class="sxs-lookup"><span data-stu-id="1c6b0-116">Your favorite code editor</span></span>

---

## <a name="getting-started"></a><span data-ttu-id="1c6b0-117">시작</span><span class="sxs-lookup"><span data-stu-id="1c6b0-117">Getting started</span></span>

<span data-ttu-id="1c6b0-118">다음 예제에서는 .NET Core 웹 프로젝트에 웹 서비스 참조를 추가하고 서비스를 호출하는 데 필요한 단계를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-118">The following example walks you through the steps required to add a web service reference to a .NET Core web project and invoke the service.</span></span> <span data-ttu-id="1c6b0-119">*HelloSvcutil*이라는 .NET Core 웹 애플리케이션을 만들고 다음 계약을 구현하는 웹 서비스에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-119">You'll create a .NET Core web application named *HelloSvcutil* and add a reference to a web service that implements the following contract:</span></span>

```csharp
[ServiceContract]
public interface ISayHello
{
    [OperationContract]
    string Hello(string name);
}
```

<span data-ttu-id="1c6b0-120">이 예제에서는 웹 서비스가 `http://contoso.com/SayHello.svc` 주소에서 호스트되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-120">For this example, let's assume the web service will be hosted at the following address: `http://contoso.com/SayHello.svc`</span></span>

<span data-ttu-id="1c6b0-121">Windows, macOS 또는 Linux 명령 창에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-121">From a Windows, macOS, or Linux command window perform the following steps:</span></span>

1. <span data-ttu-id="1c6b0-122">프로젝트에 대해 _HelloSvcutil_ 디렉터리를 만들고 다음 예제와 같이 현재 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-122">Create a directory named _HelloSvcutil_ for your project and make it your current directory, as in the following example:</span></span>

    ```console
    mkdir HelloSvcutil
    cd HelloSvcutil
    ```

2. <span data-ttu-id="1c6b0-123">다음과 같이 [`dotnet new`](../tools/dotnet-new.md) 명령을 사용하여 이 디렉터리에서 새 C# 웹 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-123">Create a new C# web project in that directory using the [`dotnet new`](../tools/dotnet-new.md) command as follows:</span></span>

    ```dotnetcli
    dotnet new web
    ```

3. <span data-ttu-id="1c6b0-124">[`dotnet-svcutil` NuGet 패키지](https://nuget.org/packages/dotnet-svcutil)를 CLI 도구( )로 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-124">Install the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool:  </span></span><!-- markdownlint-disable MD023 -->
    # <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[<span data-ttu-id="1c6b0-125">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="1c6b0-125">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

    ```dotnetcli
    dotnet tool install --global dotnet-svcutil
    ```

    # <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[<span data-ttu-id="1c6b0-126">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="1c6b0-126">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)
    <span data-ttu-id="1c6b0-127">편집기에서 `HelloSvcutil.csproj` 프로젝트 파일을 열고, `Project` 요소를 편집하고, 다음 코드를 사용하여 [`dotnet-svcutil` NuGet 패키지](https://nuget.org/packages/dotnet-svcutil)를 CLI 도구 참조로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-127">Open the `HelloSvcutil.csproj` project file in your editor, edit the `Project` element, and add the [`dotnet-svcutil` NuGet package](https://nuget.org/packages/dotnet-svcutil) as a CLI tool reference, using the following code:</span></span>

    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil" Version="1.0.*" />
    </ItemGroup>
    ```

    <span data-ttu-id="1c6b0-128">그리고 다음과 같이 [`dotnet restore`](../tools/dotnet-restore.md) 명령을 사용하여 _dotnet-svcutil_ 패키지를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-128">Then restore the _dotnet-svcutil_ package using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

    ```dotnetcli
    dotnet restore
    ```

    ---

4. <span data-ttu-id="1c6b0-129">다음과 같이 _dotnet-svcutil_ 명령을 실행하여 웹 서비스 참조 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-129">Run the _dotnet-svcutil_ command to generate the web service reference file as follows:</span></span>

    # <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[<span data-ttu-id="1c6b0-130">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="1c6b0-130">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

    ```dotnetcli
    dotnet-svcutil http://contoso.com/SayHello.svc
    ```

    # <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[<span data-ttu-id="1c6b0-131">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="1c6b0-131">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

    ```dotnetcli
    dotnet svcutil http://contoso.com/SayHello.svc
    ```

    ---

<span data-ttu-id="1c6b0-132">생성된 파일은 _HelloSvcutil/ServiceReference/Reference.cs_로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-132">The generated file is saved as _HelloSvcutil/ServiceReference/Reference.cs_.</span></span> <span data-ttu-id="1c6b0-133">또한 _dotnet-svcutil_ 도구는 프록시 코드에 필요한 적절한 WCF 패키지를 프로젝트에 패키지 참조로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-133">The _dotnet-svcutil_ tool also adds to the project the appropriate WCF packages required by the proxy code as package references.</span></span>

## <a name="using-the-service-reference"></a><span data-ttu-id="1c6b0-134">서비스 참조 사용</span><span class="sxs-lookup"><span data-stu-id="1c6b0-134">Using the Service Reference</span></span>

1. <span data-ttu-id="1c6b0-135">다음과 같이 [`dotnet restore`](../tools/dotnet-restore.md) 명령을 사용하여 WCF 패키지를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-135">Restore the WCF packages using the [`dotnet restore`](../tools/dotnet-restore.md) command as follows:</span></span>

    ```dotnetcli
    dotnet restore
    ```

2. <span data-ttu-id="1c6b0-136">사용하려는 클라이언트 클래스 및 작업의 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-136">Find the name of the client class and operation you want to use.</span></span> <span data-ttu-id="1c6b0-137">`Reference.cs`는 `System.ServiceModel.ClientBase`에서 상속되는 클래스와 서비스에서 작업을 호출하는 데 사용할 수 있는 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-137">`Reference.cs` will contain a class that inherits from `System.ServiceModel.ClientBase`, with methods that can be used to call operations on the service.</span></span> <span data-ttu-id="1c6b0-138">이 예제에서는 _SayHello_ 서비스의 _Hello_ 작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-138">In this example, you want to call the _SayHello_ service's _Hello_ operation.</span></span> <span data-ttu-id="1c6b0-139">`ServiceReference.SayHelloClient`는 클라이언트 클래스의 이름이고, 작업을 호출하는 데 사용할 수 있는 `HelloAsync`라는 메서드를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-139">`ServiceReference.SayHelloClient` is the name of the client class, and has a method called `HelloAsync` that can be used to call the operation.</span></span>

3. <span data-ttu-id="1c6b0-140">편집기에서 `Startup.cs` 파일을 열고 상단에 서비스 참조 네임스페이스를 위한 using 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-140">Open the `Startup.cs` file in your editor, and add a using statement for the service reference namespace at the top:</span></span>

    ```csharp
    using ServiceReference;
    ```

4. <span data-ttu-id="1c6b0-141">`Configure` 메서드가 웹 서비스를 호출하도록 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-141">Edit the `Configure` method to invoke the web service.</span></span> <span data-ttu-id="1c6b0-142">이렇게 하려면 `ClientBase`에서 상속되는 클래스의 인스턴스를 만들고 클라이언트 개체에서 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-142">You do this by creating an instance of the class that inherits from `ClientBase` and calling the method on the client object:</span></span>

    ```csharp
    public void Configure(IApplicationBuilder app, IHostingEnvironment env)
    {
        if (env.IsDevelopment())
        {
            app.UseDeveloperExceptionPage();
        }

        app.Run(async (context) =>
        {
            var client = new SayHelloClient();
            var response = await client.HelloAsync();
            await context.Response.WriteAsync(response);
        });
    }

    ```

5. <span data-ttu-id="1c6b0-143">다음과 같이 [`dotnet run`](../tools/dotnet-run.md) 명령을 사용하여 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-143">Run the application using the [`dotnet run`](../tools/dotnet-run.md) command as follows:</span></span>

    ```dotnetcli
    dotnet run
    ```

6. <span data-ttu-id="1c6b0-144">웹 브라우저에서, 콘솔에 나열된 URL(예: `http://localhost:5000`)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-144">Navigate to the URL listed in the console (for example, `http://localhost:5000`) in your web browser.</span></span>

<span data-ttu-id="1c6b0-145">다음과 같은 내용이 출력됩니다. "Hello dotnet-svcutil!"</span><span class="sxs-lookup"><span data-stu-id="1c6b0-145">You should see the following output: "Hello dotnet-svcutil!"</span></span>

<span data-ttu-id="1c6b0-146">`dotnet-svcutil` 도구 매개 변수에 대한 자세한 설명을 보려면 다음과 같이 help 매개 변수를 전달하는 도구를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-146">For a detailed description of the `dotnet-svcutil` tool parameters, invoke the tool passing the help parameter as follows:</span></span>
# <a name="dotnet-svcutil-2xtabdotnetsvcutil2x"></a>[<span data-ttu-id="1c6b0-147">dotnet-svcutil 2.x</span><span class="sxs-lookup"><span data-stu-id="1c6b0-147">dotnet-svcutil 2.x</span></span>](#tab/dotnetsvcutil2x)

```dotnetcli
dotnet-svcutil --help
```

# <a name="dotnet-svcutil-1xtabdotnetsvcutil1x"></a>[<span data-ttu-id="1c6b0-148">dotnet-svcutil 1.x</span><span class="sxs-lookup"><span data-stu-id="1c6b0-148">dotnet-svcutil 1.x</span></span>](#tab/dotnetsvcutil1x)

```dotnetcli
dotnet svcutil --help
```

---

## <a name="feedback--questions"></a><span data-ttu-id="1c6b0-149">사용자 의견 및 질문</span><span class="sxs-lookup"><span data-stu-id="1c6b0-149">Feedback & questions</span></span>

<span data-ttu-id="1c6b0-150">질문이나 의견이 있는 경우 [GitHub에서 문제를 엽니다](https://github.com/dotnet/wcf/issues/new).</span><span class="sxs-lookup"><span data-stu-id="1c6b0-150">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="1c6b0-151">또한 [GitHub의 WCF 리포지토리에서](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling) 기존 질문이나 문제를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-151">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

## <a name="release-notes"></a><span data-ttu-id="1c6b0-152">릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="1c6b0-152">Release notes</span></span>

- <span data-ttu-id="1c6b0-153">알려진 문제를 비롯한 업데이트된 릴리스 정보는 [릴리스 정보](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c6b0-153">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/dotnet-svcutil-notes.md) for updated release information, including known issues.</span></span>

## <a name="information"></a><span data-ttu-id="1c6b0-154">정보</span><span class="sxs-lookup"><span data-stu-id="1c6b0-154">Information</span></span>

- [<span data-ttu-id="1c6b0-155">dotnet-svcutil NuGet 패키지</span><span class="sxs-lookup"><span data-stu-id="1c6b0-155">dotnet-svcutil NuGet Package</span></span>](https://nuget.org/packages/dotnet-svcutil)
