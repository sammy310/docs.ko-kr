---
title: DLL 함수 호출
description: 혼란스러울 수 있는 DLL 함수 호출에 대한 문제를 검토합니다. 반환 형식이 blittable인지 여부에 따라 함수 호출 프로세스가 다릅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged functions, calling
- unmanaged functions
- COM interop, platform invoke
- platform invoke, calling unmanaged functions
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 113646de-7ea0-4f0e-8df0-c46dab3e8733
ms.openlocfilehash: 09dd9d30c29660231feee6c624a025ade1fda1d3
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96282953"
---
# <a name="calling-a-dll-function"></a><span data-ttu-id="2cd8d-104">DLL 함수 호출</span><span class="sxs-lookup"><span data-stu-id="2cd8d-104">Calling a DLL Function</span></span>

<span data-ttu-id="2cd8d-105">관리되지 않는 DLL 함수 호출은 다른 관리 코드 호출과 거의 동일하지만 처음에 DLL 함수를 혼동하게 만드는 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd8d-105">Although calling unmanaged DLL functions is nearly identical to calling other managed code, there are differences that can make DLL functions seem confusing at first.</span></span> <span data-ttu-id="2cd8d-106">이 섹션에서는 몇 가지 비정상적인 호출 관련 문제를 설명하는 항목을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd8d-106">This section introduces topics that describe some of the unusual calling-related issues.</span></span>  
  
 <span data-ttu-id="2cd8d-107">플랫폼 호출에서 반환되는 구조는 관리 코드와 비관리 코드에 동일한 표현이 있는 데이터 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd8d-107">Structures that are returned from platform invoke calls must be data types that have the same representation in managed and unmanaged code.</span></span> <span data-ttu-id="2cd8d-108">이러한 형식은 변환이 필요하지 않으므로 *blittable 형식* 이라고 합니다([blittable 형식 및 비 Blittable 형식](blittable-and-non-blittable-types.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="2cd8d-108">Such types are called *blittable types* because they do not require conversion (see [Blittable and Non-Blittable Types](blittable-and-non-blittable-types.md)).</span></span> <span data-ttu-id="2cd8d-109">비 blittable 구조를 반환 형식으로 사용하는 함수를 호출하려면 비 blittable 형식과 동일한 크기의 blittable 도우미 형식을 정의하고 함수가 반환된 후 데이터를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd8d-109">To call a function that has a non-blittable structure as its return type, you can define a blittable helper type of the same size as the non-blittable type and convert the data after the function returns.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2cd8d-110">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2cd8d-110">In This Section</span></span>  

 [<span data-ttu-id="2cd8d-111">구조체 전달</span><span class="sxs-lookup"><span data-stu-id="2cd8d-111">Passing Structures</span></span>](passing-structures.md)  
 <span data-ttu-id="2cd8d-112">미리 정의된 레이아웃으로 데이터 구조를 전달하는 문제를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd8d-112">Identifies the issues of passing data structures with a predefined layout.</span></span>  
  
 [<span data-ttu-id="2cd8d-113">콜백 함수</span><span class="sxs-lookup"><span data-stu-id="2cd8d-113">Callback Functions</span></span>](callback-functions.md)  
 <span data-ttu-id="2cd8d-114">콜백 함수에 대한 기본 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd8d-114">Provides basic information about callback functions.</span></span>  
  
 [<span data-ttu-id="2cd8d-115">방법: 콜백 함수 구현</span><span class="sxs-lookup"><span data-stu-id="2cd8d-115">How to: Implement Callback Functions</span></span>](how-to-implement-callback-functions.md)  
 <span data-ttu-id="2cd8d-116">관리 코드에서 콜백 함수를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd8d-116">Describes how to implement callback functions in managed code.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2cd8d-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="2cd8d-117">Related Sections</span></span>  

 [<span data-ttu-id="2cd8d-118">관리되지 않는 DLL 함수 사용</span><span class="sxs-lookup"><span data-stu-id="2cd8d-118">Consuming Unmanaged DLL Functions</span></span>](consuming-unmanaged-dll-functions.md)  
 <span data-ttu-id="2cd8d-119">플랫폼 호출을 사용하여 관리되지 않는 DLL 함수를 호출하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd8d-119">Describes how to call unmanaged DLL functions using platform invoke.</span></span>  
  
 [<span data-ttu-id="2cd8d-120">플랫폼 호출을 사용하여 데이터 마샬링</span><span class="sxs-lookup"><span data-stu-id="2cd8d-120">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="2cd8d-121">메서드 매개 변수를 선언하고 관리되지 않는 라이브러리에서 내보낸 함수에 인수를 전달하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd8d-121">Describes how to declare method parameters and pass arguments to functions exported by unmanaged libraries.</span></span>
