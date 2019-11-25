---
title: 런타임 구성
description: 런타임 구성 설정을 사용하여 .NET Core 애플리케이션을 구성하는 방법을 알아봅니다.
ms.date: 11/13/2019
ms.openlocfilehash: f7074b07bdd5aca23b6caae78952d630d905c489
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283965"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="2bd78-103">.NET Core 런타임 구성 설정</span><span class="sxs-lookup"><span data-stu-id="2bd78-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="2bd78-104">.NET Core에서는 구성 파일 및 환경 변수를 사용하여 런타임에 .NET Core 애플리케이션의 동작을 구성할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="2bd78-105">런타임 구성은 다음과 같은 경우에 유용한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="2bd78-106">애플리케이션의 소스 코드를 소유하거나 제어하지 않으므로 프로그래밍 방식으로 해당 소스 코드를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="2bd78-107">애플리케이션의 여러 인스턴스가 단일 시스템에서 동시에 실행되며 최적의 성능을 위해 각 인스턴스를 구성하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="2bd78-108">이 설명서는 진행 중인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-108">This documentation is a work in progress.</span></span> <span data-ttu-id="2bd78-109">여기에 제공된 정보가 불완전하거나 부정확한 경우에는 [이슈를 열어](https://github.com/dotnet/docs/issues) 그에 대해 알려주시거나 [끌어오기 요청을 제출](https://github.com/dotnet/docs/pulls)하여 이슈를 해결하세요.</span><span class="sxs-lookup"><span data-stu-id="2bd78-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="2bd78-110">dotnet/docs 리포지토리에 대한 끌어오기 요청 제출에 대한 자세한 내용은 [기여자 가이드](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2bd78-110">For information on submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>

<span data-ttu-id="2bd78-111">.NET Core는 런타임에 애플리케이션을 구성하는 다음과 같은 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-111">.NET Core provides the following mechanisms for configuring applications at run time:</span></span>

- <span data-ttu-id="2bd78-112">[runtimeconfig.json 파일](#runtimeconfigjson)</span><span class="sxs-lookup"><span data-stu-id="2bd78-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="2bd78-113">환경 변수</span><span class="sxs-lookup"><span data-stu-id="2bd78-113">Environment variables</span></span>](#environment-variables)

<span data-ttu-id="2bd78-114">설명서의 이 섹션에 포함된 문서는 디버깅 및 가비지 수집 같은 범주별로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-114">The articles in this section of the documentation include are organized by category, for example, debugging and garbage collection.</span></span> <span data-ttu-id="2bd78-115">사용 가능한 구성 옵션은 *runtimeconfig.json*(.NET Core에만 해당), *app.config*(.NET Framework에만 해당) 및 환경 변수에 대해 표시되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-115">Available configuration options are shown for *runtimeconfig.json* (.NET Core only), *app.config* (.NET Framework only), and environment variables.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="2bd78-116">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="2bd78-116">runtimeconfig.json</span></span>

<span data-ttu-id="2bd78-117">*runtimeconfig.json* 파일의 **configProperties** 섹션에 런타임 구성 옵션을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-117">Specify run-time configuration options in the **configProperties** section of the *runtimeconfig.json* file.</span></span> <span data-ttu-id="2bd78-118">이 섹션은 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-118">This section has the form:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "config-property-name1": "config-value1",
         "config-property-name2": "config-value2"
      }
   }
}
```

<span data-ttu-id="2bd78-119">예제 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-119">Here is an example file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": true,
         "System.GC.RetainVM": true,
         "System.Threading.ThreadPool.MinThreads": "4",
         "System.Threading.ThreadPool.MaxThreads": "25"
      }
   }
}
```

<span data-ttu-id="2bd78-120">*runtimeconfig.json* 파일은 [dotnet build](../tools/dotnet-build.md) 명령에 의해 빌드 디렉터리에 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-120">The *runtimeconfig.json* file is automatically created in the build directory by the [dotnet build](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="2bd78-121">Visual Studio에서 **빌드** 메뉴 옵션을 선택하는 경우에도 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-121">It's also created when you select the **Build** menu option in Visual Studio.</span></span> <span data-ttu-id="2bd78-122">그러면 파일이 만들어진 후 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-122">You can then edit the file once it's created.</span></span>

<span data-ttu-id="2bd78-123">일부 구성 값은 <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> 메서드를 호출하여 프로그래밍 방식으로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-123">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="2bd78-124">환경 변수</span><span class="sxs-lookup"><span data-stu-id="2bd78-124">Environment variables</span></span>

<span data-ttu-id="2bd78-125">환경 변수를 사용하여 일부 런타임 구성 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-125">Environment variables can be used to to supply some run-time configuration information.</span></span> <span data-ttu-id="2bd78-126">환경 변수로 지정된 구성 노브는 일반적으로 **COMPlus_** 접두사가 붙어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-126">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="2bd78-127">Windows 제어판, 명령줄 또는 Windows 및 Unix 기반 시스템에서 <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> 메서드를 호출하여 프로그래밍 방식으로 환경 변수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-127">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="2bd78-128">다음 예제는 명령줄에서 환경 변수를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2bd78-128">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
