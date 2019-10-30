---
title: 다중 파일 어셈블리
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
ms.openlocfilehash: 8ffb0482ebd01a056d9ffd80a74ec0332e1b8dff
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119789"
---
# <a name="multifile-assemblies"></a><span data-ttu-id="cf7f9-102">다중 파일 어셈블리</span><span class="sxs-lookup"><span data-stu-id="cf7f9-102">Multifile assemblies</span></span>

<span data-ttu-id="cf7f9-103">명령줄 컴파일러 또는 Visual Studio를 Visual C++와 함께 사용하여 .NET Framework를 대상으로 하는 다중 파일 어셈블리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-103">You can create multifile assemblies that target the .NET Framework using command-line compilers or Visual Studio with Visual C++.</span></span> <span data-ttu-id="cf7f9-104">어셈블리의 한 파일에 어셈블리 매니페스트가 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-104">One file in the assembly must contain the assembly manifest.</span></span> <span data-ttu-id="cf7f9-105">애플리케이션을 시작하는 어셈블리에는 `Main` 또는 `WinMain` 메서드와 같은 진입점도 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-105">An assembly that starts an application must also contain an entry point, such as a `Main` or `WinMain` method.</span></span>

<span data-ttu-id="cf7f9-106">예를 들어 두 개의 코드 모듈 *Client.cs* 및 *Stringer.cs*를 포함하는 애플리케이션이 있다고 가정해 보세요.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-106">For example, suppose you have an application that contains two code modules, *Client.cs* and *Stringer.cs*.</span></span> <span data-ttu-id="cf7f9-107">*Stringer.cs*는 *Client.cs*의 코드에서 참조하는 `myStringer` 네임스페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-107">*Stringer.cs* creates the `myStringer` namespace that is referenced by the code in *Client.cs*.</span></span> <span data-ttu-id="cf7f9-108">*Client.cs*에는 애플리케이션의 진입점인 `Main` 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-108">*Client.cs* contains the `Main` method, which is the application's entry point.</span></span> <span data-ttu-id="cf7f9-109">이 예제에서는 두 개의 코드 모듈을 컴파일한 다음 애플리케이션을 시작하는 어셈블리 매니페스트가 포함된 세 번째 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-109">In this example, you compile the two code modules, and then create a third file that contains the assembly manifest, which launches the application.</span></span> <span data-ttu-id="cf7f9-110">어셈블리 매니페스트는 *Client* 및 *Stringer*모듈을 모두 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-110">The assembly manifest references both the *Client* and *Stringer* modules.</span></span>

> [!NOTE]
> <span data-ttu-id="cf7f9-111">다중 파일 어셈블리는 어셈블리에 여러 개의 코드 모듈이 있는 경우에도 진입점을 하나만 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-111">Multifile assemblies can have only one entry point, even if the assembly has multiple code modules.</span></span>

<span data-ttu-id="cf7f9-112">다중 파일 어셈블리를 만드는 것이 좋은 몇 가지 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-112">There are several reasons you might want to create a multifile assembly:</span></span>

- <span data-ttu-id="cf7f9-113">서로 다른 언어로 작성된 모듈을 결합하기 위해.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-113">To combine modules written in different languages.</span></span> <span data-ttu-id="cf7f9-114">다중 파일 어셈블리를 만드는 가장 일반적인 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-114">This is the most common reason for creating a multifile assembly.</span></span>

- <span data-ttu-id="cf7f9-115">필요할 때만 다운로드되는 모듈에 거의 사용하지 않는 형식을 삽입하여 애플리케이션 다운로드를 최적화하기 위해.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-115">To optimize downloading an application by putting seldom-used types in a module that is downloaded only when needed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf7f9-116">Microsoft Internet Explorer와 함께 `<object>` 태그를 사용하여 다운로드되는 애플리케이션을 만드는 경우 다중 파일 어셈블리를 만드는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-116">If you are creating applications that will be downloaded using the `<object>` tag with Microsoft Internet Explorer, it is important that you create multifile assemblies.</span></span> <span data-ttu-id="cf7f9-117">이 시나리오에서는 코드 모듈과 별도로 어셈블리 매니페스트만 포함된 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-117">In this scenario, you create a file separate from your code modules that contains only the assembly manifest.</span></span> <span data-ttu-id="cf7f9-118">Internet Explorer는 어셈블리 매니페스트를 먼저 다운로드한 다음 필요한 추가 모듈이나 어셈블리를 다운로드할 작업자 스레드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-118">Internet Explorer downloads the assembly manifest first, and then creates worker threads to download any additional modules or assemblies required.</span></span> <span data-ttu-id="cf7f9-119">어셈블리 매니페스트가 포함된 파일을 다운로드하는 동안 Internet Explorer는 사용자 입력에 응답하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-119">While the file containing the assembly manifest is being downloaded, Internet Explorer will be unresponsive to user input.</span></span> <span data-ttu-id="cf7f9-120">어셈블리 매니페스트가 포함된 파일이 작을수록 Internet Explorer가 응답하지 않는 시간이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-120">The smaller the file containing the assembly manifest, the less time Internet Explorer will be unresponsive.</span></span>

- <span data-ttu-id="cf7f9-121">여러 개발자가 작성한 코드 모듈을 결합하기 위해.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-121">To combine code modules written by several developers.</span></span> <span data-ttu-id="cf7f9-122">각 개발자가 각 코드 모듈을 어셈블리로 컴파일할 수 있지만 이 경우 모든 모듈을 다중 파일 어셈블리에 포함할 경우 노출되지 않는 일부 형식이 강제로 공개될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-122">Although each developer can compile each code module into an assembly, this can force some types to be exposed publicly that are not exposed if all modules are put into a multifile assembly.</span></span>

<span data-ttu-id="cf7f9-123">어셈블리를 만든 후 어셈블리 매니페스트가 포함된 파일(따라서 어셈블리)에 서명하거나 파일 및 어셈블리에 강력한 이름을 지정하고 전역 어셈블리 캐시에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf7f9-123">Once you create the assembly, you can sign the file that contains the assembly manifest, and hence the assembly, or you can give the file and the assembly a strong name and put it in the global assembly cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf7f9-124">참조</span><span class="sxs-lookup"><span data-stu-id="cf7f9-124">See also</span></span>

- [<span data-ttu-id="cf7f9-125">방법: 다중 파일 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="cf7f9-125">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="cf7f9-126">어셈블리를 사용한 프로그램</span><span class="sxs-lookup"><span data-stu-id="cf7f9-126">Program with assemblies</span></span>](../../standard/assembly/program.md)
