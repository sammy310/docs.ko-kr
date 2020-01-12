---
title: dotnet vstest로 게시된 출력 테스트
description: dotnet vstest 명령을 사용하여 소스 코드 대신, 게시된 라이브러리에 대해 테스트를 실행하는 방법을 알아봅니다.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: 7618d37782de3a16f1963380bbb56945fb73e8eb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714263"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="30947-103">dotnet vstest로 게시된 출력 테스트</span><span class="sxs-lookup"><span data-stu-id="30947-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="30947-104">`dotnet vstest` 명령을 사용하여 이미 게시된 출력에 대해 테스트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30947-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="30947-105">이는 xUnit, MSTest 및 NUnit 테스트에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="30947-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="30947-106">게시된 출력의 일부인 DLL 파일을 찾아 실행하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="30947-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```dotnetcli
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="30947-107">여기서 `<MyPublishedTests>`는 게시된 테스트 프로젝트의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="30947-107">Where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example"></a><span data-ttu-id="30947-108">예제</span><span class="sxs-lookup"><span data-stu-id="30947-108">Example</span></span>

<span data-ttu-id="30947-109">아래 명령은 게시된 DLL에서 실행 중인 테스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="30947-109">The commands below demonstrate running tests on a published DLL.</span></span>

```dotnetcli
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="30947-110">참고: 앱이 `netcoreapp` 이외의 프레임워크를 대상으로 하는 경우 프레임워크 플래그로 대상 프레임워크를 전달하여 `dotnet vstest` 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30947-110">Note: If your app targets a framework other than `netcoreapp`, you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="30947-111">예: `dotnet vstest <MyPublishedTests>.dll --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="30947-111">For example, `dotnet vstest <MyPublishedTests>.dll --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="30947-112">Visual Studio 2017 업데이트 5 이상에서는 필요한 프레임워크가 자동으로 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="30947-112">In Visual Studio 2017 Update 5 and later, the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="30947-113">참조</span><span class="sxs-lookup"><span data-stu-id="30947-113">See also</span></span>

- [<span data-ttu-id="30947-114">dotnet 테스트 및 xUnit을 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="30947-114">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="30947-115">dotnet 테스트 및 NUnit을 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="30947-115">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="30947-116">dotnet 테스트 및 MSTest를 사용한 단위 테스트</span><span class="sxs-lookup"><span data-stu-id="30947-116">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
