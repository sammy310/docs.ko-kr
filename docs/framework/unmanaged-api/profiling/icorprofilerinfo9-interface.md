---
title: ICorProfilerInfo9 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 74031fd822550f8a0752d02ce0c2d89b2f5ae546
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444957"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="42dfa-102">ICorProfilerInfo9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42dfa-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="42dfa-103">A subclass of [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span><span class="sxs-lookup"><span data-stu-id="42dfa-103">A subclass of [ICorProfilerInfo8](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="42dfa-104">메서드</span><span class="sxs-lookup"><span data-stu-id="42dfa-104">Methods</span></span>  

| <span data-ttu-id="42dfa-105">메서드</span><span class="sxs-lookup"><span data-stu-id="42dfa-105">Method</span></span>|<span data-ttu-id="42dfa-106">설명</span><span class="sxs-lookup"><span data-stu-id="42dfa-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="42dfa-107">GetNativeCodeStartAddresses Method</span><span class="sxs-lookup"><span data-stu-id="42dfa-107">GetNativeCodeStartAddresses Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="42dfa-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span><span class="sxs-lookup"><span data-stu-id="42dfa-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="42dfa-109">GetILToNativeMapping3 Method</span><span class="sxs-lookup"><span data-stu-id="42dfa-109">GetILToNativeMapping3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="42dfa-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span><span class="sxs-lookup"><span data-stu-id="42dfa-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="42dfa-111">GetCodeInfo4 Method</span><span class="sxs-lookup"><span data-stu-id="42dfa-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="42dfa-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span><span class="sxs-lookup"><span data-stu-id="42dfa-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="42dfa-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="42dfa-113">Requirements</span></span>  
<span data-ttu-id="42dfa-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="42dfa-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>  
<span data-ttu-id="42dfa-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="42dfa-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="42dfa-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42dfa-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="42dfa-117">참조</span><span class="sxs-lookup"><span data-stu-id="42dfa-117">See also</span></span>

- [<span data-ttu-id="42dfa-118">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="42dfa-118">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
