---
title: 프로파일링 구조체
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: 2f3e8cedcc498230311c0b52f7ecc1c2c4fc8ff1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447701"
---
# <a name="profiling-structures"></a><span data-ttu-id="d0d93-102">프로파일링 구조체</span><span class="sxs-lookup"><span data-stu-id="d0d93-102">Profiling Structures</span></span>
<span data-ttu-id="d0d93-103">이 섹션에서는 프로파일링 API에서 사용하는 관리되지 않는 구조체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d93-103">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d0d93-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d0d93-104">In This Section</span></span>  
 [<span data-ttu-id="d0d93-105">COR_PRF_ASSEMBLY_REFERENCE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="d0d93-105">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="d0d93-106">어셈블리 참조 closure 워커를 수행할 때 고려해야 하는 참조 어셈블리에 대한 정보를 공용 언어 런타임에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d93-106">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="d0d93-107">COR_PRF_CODE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="d0d93-107">COR_PRF_CODE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)  
 <span data-ttu-id="d0d93-108">메모리 내에 저장된 연속하는 네이티브 코드 블록 하나를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0d93-108">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="d0d93-109">COR_PRF_EX_CLAUSE_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="d0d93-109">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="d0d93-110">특정 예외 절 인스턴스 및 관련 프레임에 대한 정보를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d93-110">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="d0d93-111">COR_PRF_FUNCTION 구조체</span><span class="sxs-lookup"><span data-stu-id="d0d93-111">COR_PRF_FUNCTION Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-structure.md)  
 <span data-ttu-id="d0d93-112">함수의 ID와 다시 컴파일된 함수 버전의 ID를 결합하여 함수의 고유한 표현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d93-112">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="d0d93-113">COR_PRF_FUNCTION_ARGUMENT_INFO 구조체</span><span class="sxs-lookup"><span data-stu-id="d0d93-113">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="d0d93-114">왼쪽에서 오른쪽 순서의 함수 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0d93-114">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="d0d93-115">COR_PRF_FUNCTION_ARGUMENT_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="d0d93-115">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="d0d93-116">왼쪽에서 오른쪽 순서로 연속적으로 메모리에 저장한 함수 인수 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d0d93-116">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="d0d93-117">COR_PRF_GC_GENERATION_RANGE 구조체</span><span class="sxs-lookup"><span data-stu-id="d0d93-117">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="d0d93-118">가비지 수집이 진행 중인 메모리 범위(블록)를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d93-118">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d0d93-119">관련 단원</span><span class="sxs-lookup"><span data-stu-id="d0d93-119">Related Sections</span></span>  
 <span data-ttu-id="d0d93-120">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="d0d93-120">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="d0d93-121">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="d0d93-121">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="d0d93-122">프로파일링 개요</span><span class="sxs-lookup"><span data-stu-id="d0d93-122">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="d0d93-123">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0d93-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="d0d93-124">프로파일링 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="d0d93-124">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="d0d93-125">프로파일링 열거형</span><span class="sxs-lookup"><span data-stu-id="d0d93-125">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
