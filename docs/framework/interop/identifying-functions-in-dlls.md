---
title: DLL 함수 식별
description: DLL에서 함수를 식별합니다. DLL 함수 ID는 함수 이름 또는 서수와 구현을 찾을 수 있는 DLL 파일 이름으로 구성됩니다.
ms.date: 03/30/2017
helpviewer_keywords:
- platform invoke, identifying functions
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- identifying DLL functions
- DLL functions
ms.assetid: 3e3f6780-6d90-4413-bad7-ba641220364d
ms.openlocfilehash: b1d95329e9b8ac6cd1f8ffc3111a50b6ab010462
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96281718"
---
# <a name="identifying-functions-in-dlls"></a><span data-ttu-id="6b3a3-104">DLL 함수 식별</span><span class="sxs-lookup"><span data-stu-id="6b3a3-104">Identifying Functions in DLLs</span></span>

<span data-ttu-id="6b3a3-105">DLL 함수 ID는 다음 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-105">The identity of a DLL function consists of the following elements:</span></span>  
  
- <span data-ttu-id="6b3a3-106">함수 이름 또는 서수</span><span class="sxs-lookup"><span data-stu-id="6b3a3-106">Function name or ordinal</span></span>  
  
- <span data-ttu-id="6b3a3-107">구현을 찾을 수 있는 DLL 파일의 이름</span><span class="sxs-lookup"><span data-stu-id="6b3a3-107">Name of the DLL file in which the implementation can be found</span></span>  
  
 <span data-ttu-id="6b3a3-108">예를 들어 User32.dll의 **MessageBox** 함수는 함수(**MessageBox**) 및 해당 위치(User32.dll, User32 또는 user32)를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-108">For example, specifying the **MessageBox** function in the User32.dll identifies the function (**MessageBox**) and its location (User32.dll, User32, or user32).</span></span> <span data-ttu-id="6b3a3-109">Microsoft Windows 애플리케이션 프로그래밍 인터페이스(Windows API)에는 문자와 문자열을 처리하는 각 함수의 두 가지 버전인 1바이트 문자 ANSI 버전 및 2바이트 문자 유니코드 버전이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-109">The Microsoft Windows application programming interface (Windows API) can contain two versions of each function that handles characters and strings: a 1-byte character ANSI version and a 2-byte character Unicode version.</span></span> <span data-ttu-id="6b3a3-110">지정하지 않을 경우 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> 필드로 표현되는 문자 집합은 기본적으로 ANSI로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-110">When unspecified, the character set, represented by the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field, defaults to ANSI.</span></span> <span data-ttu-id="6b3a3-111">일부 함수에는 버전이 세 개 이상 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-111">Some functions can have more than two versions.</span></span>  
  
 <span data-ttu-id="6b3a3-112">**MessageBoxA** 는 **MessageBox** 함수의 ANSI 진입점이고 **MessageBoxW** 는 유니코드 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-112">**MessageBoxA** is the ANSI entry point for the **MessageBox** function; **MessageBoxW** is the Unicode version.</span></span> <span data-ttu-id="6b3a3-113">다양한 명령줄 도구를 실행하여 user32.dll과 같은 특정 DLL에 대한 함수 이름을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-113">You can list function names for a specific DLL, such as user32.dll, by running a variety of command-line tools.</span></span> <span data-ttu-id="6b3a3-114">예를 들어 `dumpbin /exports user32.dll` 또는 `link /dump /exports user32.dll`을 사용하여 함수 이름을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-114">For example, you can use `dumpbin /exports user32.dll` or `link /dump /exports user32.dll` to obtain function names.</span></span>  
  
 <span data-ttu-id="6b3a3-115">DLL에서 새 이름을 원래 진입점에 매핑할 경우 코드 내에서 관리되지 않는 함수의 이름을 원하는 대로 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-115">You can rename an unmanaged function to whatever you like within your code as long as you map the new name to the original entry point in the DLL.</span></span> <span data-ttu-id="6b3a3-116">관리 소스 코드에서 관리되지 않는 DLL 함수의 이름을 바꾸는 방법에 대한 자세한 내용은 [진입점 지정](specifying-an-entry-point.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-116">For instructions on renaming an unmanaged DLL function in managed source code, see the [Specifying an Entry Point](specifying-an-entry-point.md).</span></span>  
  
 <span data-ttu-id="6b3a3-117">플랫폼 호출을 사용하면 Windows API 및 기타 DLL의 함수를 호출하여 운영 체제의 상당한 부분을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-117">Platform invoke enables you to control a significant portion of the operating system by calling functions in the Windows API and other DLLs.</span></span> <span data-ttu-id="6b3a3-118">Windows API 이외에 플랫폼 호출을 통해 사용할 수 있는 수많은 기타 API 및 DLL이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-118">In addition to the Windows API, there are numerous other APIs and DLLs available to you through platform invoke.</span></span>  
  
 <span data-ttu-id="6b3a3-119">다음 표에서는 Windows API에서 일반적으로 사용되는 여러 DLL을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-119">The following table describes several commonly used DLLs in the Windows API.</span></span>  
  
|<span data-ttu-id="6b3a3-120">DLL</span><span class="sxs-lookup"><span data-stu-id="6b3a3-120">DLL</span></span>|<span data-ttu-id="6b3a3-121">콘텐츠 설명</span><span class="sxs-lookup"><span data-stu-id="6b3a3-121">Description of Contents</span></span>|  
|---------|-----------------------------|  
|<span data-ttu-id="6b3a3-122">GDI32.dll</span><span class="sxs-lookup"><span data-stu-id="6b3a3-122">GDI32.dll</span></span>|<span data-ttu-id="6b3a3-123">디바이스 출력을 위한 GDI(그래픽 디바이스 인터페이스) 함수입니다(예: 그리기 및 글꼴 관리용 함수).</span><span class="sxs-lookup"><span data-stu-id="6b3a3-123">Graphics Device Interface (GDI) functions for device output, such as those for drawing and font management.</span></span>|  
|<span data-ttu-id="6b3a3-124">Kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="6b3a3-124">Kernel32.dll</span></span>|<span data-ttu-id="6b3a3-125">메모리 관리 및 리소스 처리를 위한 하위 수준 운영 체제 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-125">Low-level operating system functions for memory management and resource handling.</span></span>|  
|<span data-ttu-id="6b3a3-126">User32.dll</span><span class="sxs-lookup"><span data-stu-id="6b3a3-126">User32.dll</span></span>|<span data-ttu-id="6b3a3-127">메시지 처리, 타이머, 메뉴 및 통신을 위한 Windows 관리 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-127">Windows management functions for message handling, timers, menus, and communications.</span></span>|  
  
 <span data-ttu-id="6b3a3-128">Windows API에 대한 전체 설명서는 플랫폼 SDK를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-128">For complete documentation on the Windows API, see the Platform SDK.</span></span> <span data-ttu-id="6b3a3-129">플랫폼 호출에서 사용되는 .NET 기반 선언을 생성하는 방법을 보여 주는 예제는 [플랫폼 호출을 사용하여 데이터 마샬링](marshaling-data-with-platform-invoke.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b3a3-129">For examples that demonstrate how to construct .NET-based declarations to be used with platform invoke, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b3a3-130">참조</span><span class="sxs-lookup"><span data-stu-id="6b3a3-130">See also</span></span>

- [<span data-ttu-id="6b3a3-131">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="6b3a3-131">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)
- [<span data-ttu-id="6b3a3-132">진입점 지정</span><span class="sxs-lookup"><span data-stu-id="6b3a3-132">Specifying an Entry Point</span></span>](specifying-an-entry-point.md)
- [<span data-ttu-id="6b3a3-133">DLL 함수가 포함된 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="6b3a3-133">Creating a Class to Hold DLL Functions</span></span>](creating-a-class-to-hold-dll-functions.md)
- [<span data-ttu-id="6b3a3-134">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="6b3a3-134">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="6b3a3-135">DLL 함수 호출</span><span class="sxs-lookup"><span data-stu-id="6b3a3-135">Calling a DLL Function</span></span>](calling-a-dll-function.md)
