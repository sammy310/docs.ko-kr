---
description: '자세한 정보: 프로 파일링 구조'
title: 프로파일링 구조체
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: 176830cac519f22864ba004b176cb575d80e50e2
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760238"
---
# <a name="profiling-structures"></a><span data-ttu-id="cb9ad-103">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="cb9ad-103">Profiling Structures</span></span>

<span data-ttu-id="cb9ad-104">이 섹션에서는 프로파일링 API에서 사용하는 관리되지 않는 구조체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-104">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cb9ad-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="cb9ad-105">In This Section</span></span>  

 [<span data-ttu-id="cb9ad-106">COR_PRF_ASSEMBLY_REFERENCE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="cb9ad-106">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="cb9ad-107">어셈블리 참조 closure 워커를 수행할 때 고려해야 하는 참조 어셈블리에 대한 정보를 공용 언어 런타임에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-107">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="cb9ad-108">COR_PRF_CODE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="cb9ad-108">COR_PRF_CODE_INFO Structure</span></span>](cor-prf-code-info-structure.md)  
 <span data-ttu-id="cb9ad-109">메모리 내에 저장된 연속하는 네이티브 코드 블록 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-109">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="cb9ad-110">COR_PRF_EX_CLAUSE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="cb9ad-110">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="cb9ad-111">특정 예외 절 인스턴스 및 관련 프레임에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-111">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="cb9ad-112">COR_PRF_FUNCTION 구조체</span><span class="sxs-lookup"><span data-stu-id="cb9ad-112">COR_PRF_FUNCTION Structure</span></span>](cor-prf-function-structure.md)  
 <span data-ttu-id="cb9ad-113">함수의 ID와 다시 컴파일된 함수 버전의 ID를 결합하여 함수의 고유한 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-113">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="cb9ad-114">COR_PRF_FUNCTION_ARGUMENT_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="cb9ad-114">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="cb9ad-115">왼쪽에서 오른쪽 순서의 함수 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-115">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="cb9ad-116">COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="cb9ad-116">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="cb9ad-117">왼쪽에서 오른쪽 순서로 연속적으로 메모리에 저장한 함수 인수 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-117">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="cb9ad-118">COR_PRF_GC_GENERATION_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="cb9ad-118">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="cb9ad-119">가비지 수집이 진행 중인 메모리 범위(블록)를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-119">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  

 <span data-ttu-id="cb9ad-120">[COR_PRF_EVENTPIPE_PROVIDER_CONFIG 구조체](cor-prf-eventpipe-provider-config-structure.md) EventPipe 공급자를 구성 하는 데 필요한 필드에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-120">[COR_PRF_EVENTPIPE_PROVIDER_CONFIG Structure](cor-prf-eventpipe-provider-config-structure.md) Describes the fields necessary to configure an EventPipe provider.</span></span>

 <span data-ttu-id="cb9ad-121">[COR_PRF_EVENTPIPE_PARAM_DESC 구조체](cor-prf-eventpipe-param-desc-structure.md) EventPipe 이벤트의 매개 변수 이름 및 유형을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-121">[COR_PRF_EVENTPIPE_PARAM_DESC Structure](cor-prf-eventpipe-param-desc-structure.md) Describes the parameter name and type for an EventPipe event.</span></span>

 <span data-ttu-id="cb9ad-122">[COR_PRF_EVENT_DATA 구조체](cor-prf-event-data-structure.md) 작성 중인 EventPipe 이벤트에 대 한 이벤트 데이터를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9ad-122">[COR_PRF_EVENT_DATA Structure](cor-prf-event-data-structure.md) Describes the event data for an EventPipe event being written.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="cb9ad-123">관련 단원</span><span class="sxs-lookup"><span data-stu-id="cb9ad-123">Related Sections</span></span>  

 <span data-ttu-id="cb9ad-124">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="cb9ad-124">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="cb9ad-125">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="cb9ad-125">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="cb9ad-126">프로파일링 개요</span><span class="sxs-lookup"><span data-stu-id="cb9ad-126">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="cb9ad-127">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb9ad-127">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="cb9ad-128">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="cb9ad-128">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="cb9ad-129">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="cb9ad-129">Profiling Enumerations</span></span>](profiling-enumerations.md)
