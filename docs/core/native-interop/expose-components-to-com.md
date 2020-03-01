---
title: COM에 .NET Core 구성 요소 공개
ms.date: 07/12/2019
helpviewer_keywords:
- exposing .NET Core components to COM
- interoperation with unmanaged code, exposing .NET Core components
- COM interop, exposing COM components
ms.assetid: 21271167-fe7f-46ba-a81f-a6812ea649d4
author: jkoritzinsky
ms.author: jekoritz
ms.openlocfilehash: 301177113f67748b62ea2686615cfe5378fdc2fd
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157546"
---
# <a name="exposing-net-core-components-to-com"></a><span data-ttu-id="86d19-102">COM에 .NET Core 구성 요소 공개</span><span class="sxs-lookup"><span data-stu-id="86d19-102">Exposing .NET Core components to COM</span></span>

<span data-ttu-id="86d19-103">.NET Core에서는 COM에 .NET 개체를 공개하는 절차가 .NET Framework에 비해 크게 간소화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-103">In .NET Core, the process for exposing your .NET objects to COM has been significantly streamlined in comparison to .NET Framework.</span></span> <span data-ttu-id="86d19-104">다음 절차에서는 클래스를 COM에 공개하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-104">The following process will walk you through how to expose a class to COM.</span></span> <span data-ttu-id="86d19-105">이 자습서에서는 다음을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-105">This tutorial shows you how to:</span></span>

- <span data-ttu-id="86d19-106">.NET Core에서 COM에 클래스를 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-106">Expose a class to COM from .NET Core.</span></span>
- <span data-ttu-id="86d19-107">.NET Core 라이브러리를 빌드하는 동안 COM 서버를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-107">Generate a COM server as part of building your .NET Core library.</span></span>
- <span data-ttu-id="86d19-108">레지스트리 없는 COM을 위한 병렬 서버 매니페스트를 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-108">Automatically generate a side-by-side server manifest for Registry-Free COM.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="86d19-109">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="86d19-109">Prerequisites</span></span>

- <span data-ttu-id="86d19-110">[.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) 또는 최신 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-110">Install [.NET Core 3.0 SDK](https://dotnet.microsoft.com/download) or a newer version.</span></span>

## <a name="create-the-library"></a><span data-ttu-id="86d19-111">라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="86d19-111">Create the library</span></span>

<span data-ttu-id="86d19-112">첫 번째 단계는 라이브러리를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-112">The first step is to create the library.</span></span>

1. <span data-ttu-id="86d19-113">새 폴더를 만든 다음, 해당 폴더에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-113">Create a new folder, and in that folder run the following command:</span></span>

    ```dotnetcli
    dotnet new classlib
    ```

2. <span data-ttu-id="86d19-114">`Class1.cs`를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-114">Open `Class1.cs`.</span></span>
3. <span data-ttu-id="86d19-115">`using System.Runtime.InteropServices;`를 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-115">Add `using System.Runtime.InteropServices;` to the top of the file.</span></span>
4. <span data-ttu-id="86d19-116">`IServer` 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-116">Create an interface named `IServer`.</span></span> <span data-ttu-id="86d19-117">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="86d19-117">For example:</span></span>

   [!code-csharp[The IServer interface](~/samples/core/extensions/COMServerDemo/COMContract/IServer.cs)]

5. <span data-ttu-id="86d19-118">구현 중인 COM 인터페이스의 인터페이스 GUID를 사용하여 `[Guid("<IID>")]` 특성을 인터페이스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-118">Add the `[Guid("<IID>")]` attribute to the interface, with the interface GUID for the COM interface you're implementing.</span></span> <span data-ttu-id="86d19-119">예: `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span><span class="sxs-lookup"><span data-stu-id="86d19-119">For example, `[Guid("fe103d6e-e71b-414c-80bf-982f18f6c1c7")]`.</span></span> <span data-ttu-id="86d19-120">이 GUID는 이 COM용 인터페이스의 유일한 식별자이므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-120">Note that this GUID needs to be unique since it is the only identifier of this interface for COM.</span></span> <span data-ttu-id="86d19-121">Visual Studio에서 [도구] > [GUID 만들기]로 이동하여 GUID 만들기 도구를 열고 GUID를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-121">In Visual Studio, you can generate a GUID by going to Tools > Create GUID to open the Create GUID tool.</span></span>
6. <span data-ttu-id="86d19-122">`[InterfaceType]` 특성을 인터페이스에 추가하고 이 인터페이스에서 구현해야 하는 기본 COM 인터페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-122">Add the `[InterfaceType]` attribute to the interface and specify what base COM interfaces your interface should implement.</span></span>
7. <span data-ttu-id="86d19-123">`IServer`를 구현하는 `Server`라는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-123">Create a class named `Server` that implements `IServer`.</span></span>
8. <span data-ttu-id="86d19-124">구현 중인 COM 클래스의 클래스 식별자 GUID를 사용하여 `[Guid("<CLSID>")]` 특성을 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-124">Add the `[Guid("<CLSID>")]` attribute to the class, with the class identifier GUID for the COM class you're implementing.</span></span> <span data-ttu-id="86d19-125">예: `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span><span class="sxs-lookup"><span data-stu-id="86d19-125">For example, `[Guid("9f35b6f5-2c05-4e7f-93aa-ee087f6e7ab6")]`.</span></span> <span data-ttu-id="86d19-126">인터페이스 GUID와 마찬가지로 이 GUID는 이 COM용 인터페이스의 유일한 식별자이므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-126">As with the interface GUID, this GUID must be unique since it is the only identifier of this interface to COM.</span></span>
9. <span data-ttu-id="86d19-127">인터페이스 및 클래스에 모두 `[ComVisible(true)]` 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-127">Add the `[ComVisible(true)]` attribute to both the interface and the class.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86d19-128">.NET Framework와 달리 .NET Core에서는 COM을 통해 활성화하려는 클래스의 CLSID를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-128">Unlike in .NET Framework, .NET Core requires you to specify the CLSID of any class you want to be activatable via COM.</span></span>

## <a name="generate-the-com-host"></a><span data-ttu-id="86d19-129">COM 호스트 생성</span><span class="sxs-lookup"><span data-stu-id="86d19-129">Generate the COM host</span></span>

1. <span data-ttu-id="86d19-130">`.csproj` 프로젝트 파일을 열고 `<PropertyGroup></PropertyGroup>` 태그 안에 `<EnableComHosting>true</EnableComHosting>`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-130">Open the `.csproj` project file and add `<EnableComHosting>true</EnableComHosting>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="86d19-131">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-131">Build the project.</span></span>

<span data-ttu-id="86d19-132">결과 출력에는 `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` 및 `ProjectName.comhost.dll` 파일이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-132">The resulting output will have a `ProjectName.dll`, `ProjectName.deps.json`, `ProjectName.runtimeconfig.json` and `ProjectName.comhost.dll` file.</span></span>

## <a name="register-the-com-host-for-com"></a><span data-ttu-id="86d19-133">COM용 COM 호스트 등록</span><span class="sxs-lookup"><span data-stu-id="86d19-133">Register the COM host for COM</span></span>

<span data-ttu-id="86d19-134">관리자 권한 명령 프롬프트를 열고 `regsvr32 ProjectName.comhost.dll`을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-134">Open an elevated command prompt and run `regsvr32 ProjectName.comhost.dll`.</span></span> <span data-ttu-id="86d19-135">이렇게 하면 공개된 모든 .NET 개체가 COM에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-135">That will register all of your exposed .NET objects with COM.</span></span>

## <a name="enabling-regfree-com"></a><span data-ttu-id="86d19-136">RegFree COM 사용</span><span class="sxs-lookup"><span data-stu-id="86d19-136">Enabling RegFree COM</span></span>

1. <span data-ttu-id="86d19-137">`.csproj` 프로젝트 파일을 열고 `<PropertyGroup></PropertyGroup>` 태그 안에 `<EnableRegFreeCom>true</EnableRegFreeCom>`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-137">Open the `.csproj` project file and add `<EnableRegFreeCom>true</EnableRegFreeCom>` inside a `<PropertyGroup></PropertyGroup>` tag.</span></span>
2. <span data-ttu-id="86d19-138">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-138">Build the project.</span></span>

<span data-ttu-id="86d19-139">이제 결과 출력에는 `ProjectName.X.manifest` 파일도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-139">The resulting output will now also have a `ProjectName.X.manifest` file.</span></span> <span data-ttu-id="86d19-140">이 파일은 레지스트리 없는 COM과 함께 사용할 병렬 매니페스트입니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-140">This file is the side-by-side manifest for use with Registry-Free COM.</span></span>

## <a name="sample"></a><span data-ttu-id="86d19-141">예제</span><span class="sxs-lookup"><span data-stu-id="86d19-141">Sample</span></span>

<span data-ttu-id="86d19-142">GitHub의 dotnet/samples 리포지토리에는 완벽하게 작동하는 [COM 서버 샘플](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-142">There is a fully functional [COM server sample](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo) in the dotnet/samples repository on GitHub.</span></span>

## <a name="additional-notes"></a><span data-ttu-id="86d19-143">추가 참고 사항</span><span class="sxs-lookup"><span data-stu-id="86d19-143">Additional notes</span></span>

<span data-ttu-id="86d19-144">.NET Framework와 달리 .NET Core에서는 .NET Core 어셈블리에서 COM 형식 라이브러리(TLB)를 생성하는 기능을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-144">Unlike in .NET Framework, there is no support in .NET Core for generating a COM Type Library (TLB) from a .NET Core assembly.</span></span> <span data-ttu-id="86d19-145">이 지침에서는 COM 인터페이스의 기본 선언을 위한 IDL 파일 또는 C/C++ 헤더를 수동으로 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-145">The guidance is to either manually write an IDL file or a C/C++ header for the native declarations of the COM interfaces.</span></span>

<span data-ttu-id="86d19-146">또한 .NET Framework와 .NET Core를 같은 프로세스에 로드하는 경우 진단 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-146">Additionally, loading both .NET Framework and .NET Core into the same process does have diagnostic limitations.</span></span> <span data-ttu-id="86d19-147">.NET Framework와 .NET Core를 동시에 디버그할 수 없으므로 기본 제한 사항은 관리형 구성 요소를 디버그하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-147">The primary limitation is the debugging of managed components as it is not possible to debug both .NET Framework and .NET Core at the same time.</span></span> <span data-ttu-id="86d19-148">또한 두 런타임 인스턴스는 관리형 어셈블리를 공유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-148">In addition, the two runtime instances don't share managed assemblies.</span></span> <span data-ttu-id="86d19-149">즉, 두 런타임 간에 실제 .NET 형식을 공유할 수 없으며 대신 모든 상호 작용을 노출된 COM 인터페이스 계약으로 제한해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86d19-149">This means that it isn't possible to share actual .NET types across the two runtimes and instead all interactions must be restricted to the exposed COM interface contracts.</span></span>
