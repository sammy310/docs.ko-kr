---
title: ICorProfilerInfo9 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 431a546fb4a3b92b379e273553f0caf540ba1473
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77449738"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="c8b29-102">ICorProfilerInfo9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8b29-102">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="c8b29-103">여러 네이티브 코드 버전이 있는 함수에 대 한 정보를 쿼리 하는 메서드를 제공 하는 [ICorProfilerInfo8](icorprofilerinfo8-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c8b29-103">A subclass of [ICorProfilerInfo8](icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="c8b29-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c8b29-104">Methods</span></span>  

| <span data-ttu-id="c8b29-105">방법</span><span class="sxs-lookup"><span data-stu-id="c8b29-105">Method</span></span>|<span data-ttu-id="c8b29-106">Description</span><span class="sxs-lookup"><span data-stu-id="c8b29-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="c8b29-107">GetNativeCodeStartAddresses 메서드</span><span class="sxs-lookup"><span data-stu-id="c8b29-107">GetNativeCodeStartAddresses Method</span></span>](icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="c8b29-108">FunctionId 및 rejitId가 지정 된 경우 현재 존재 하는이 코드의 모든 jit 컴파일된 버전의 네이티브 코드 시작 주소를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b29-108">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="c8b29-109">GetILToNativeMapping3 메서드</span><span class="sxs-lookup"><span data-stu-id="c8b29-109">GetILToNativeMapping3 Method</span></span>](icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="c8b29-110">네이티브 코드 시작 주소가 지정 된 경우이 jit 컴파일된 버전의 코드에 대 한 네이티브 IL 매핑 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b29-110">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="c8b29-111">GetCodeInfo4 메서드</span><span class="sxs-lookup"><span data-stu-id="c8b29-111">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="c8b29-112">네이티브 코드 시작 주소가 지정 된 경우이 코드를 저장 하는 가상 메모리 블록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8b29-112">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="c8b29-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8b29-113">Requirements</span></span>  
<span data-ttu-id="c8b29-114">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/dependencies.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8b29-114">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>  
<span data-ttu-id="c8b29-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c8b29-115">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="c8b29-116">**.Net 버전:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8b29-116">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="c8b29-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8b29-117">See also</span></span>

- [<span data-ttu-id="c8b29-118">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8b29-118">Profiling Interfaces</span></span>](profiling-interfaces.md)
