---
description: '자세히 알아보기: ICorProfilerInfo9 인터페이스'
title: ICorProfilerInfo9 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 44e3d694b426f87ee4e4bc12181f46322b0d246f
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104805677"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="fe129-103">ICorProfilerInfo9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe129-103">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="fe129-104">여러 네이티브 코드 버전이 있는 함수에 대 한 정보를 쿼리 하는 메서드를 제공 하는 [ICorProfilerInfo8](icorprofilerinfo8-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="fe129-104">A subclass of [ICorProfilerInfo8](icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="fe129-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fe129-105">Methods</span></span>  

| <span data-ttu-id="fe129-106">메서드</span><span class="sxs-lookup"><span data-stu-id="fe129-106">Method</span></span>|<span data-ttu-id="fe129-107">설명</span><span class="sxs-lookup"><span data-stu-id="fe129-107">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="fe129-108">GetNativeCodeStartAddresses 메서드</span><span class="sxs-lookup"><span data-stu-id="fe129-108">GetNativeCodeStartAddresses Method</span></span>](icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="fe129-109">FunctionId 및 rejitId가 지정 된 경우 현재 존재 하는이 코드의 모든 jit 컴파일된 버전의 네이티브 코드 시작 주소를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe129-109">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="fe129-110">GetILToNativeMapping3 메서드</span><span class="sxs-lookup"><span data-stu-id="fe129-110">GetILToNativeMapping3 Method</span></span>](icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="fe129-111">네이티브 코드 시작 주소가 지정 된 경우이 jit 컴파일된 버전의 코드에 대 한 네이티브 IL 매핑 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe129-111">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="fe129-112">GetCodeInfo4 메서드</span><span class="sxs-lookup"><span data-stu-id="fe129-112">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="fe129-113">네이티브 코드 시작 주소가 지정 된 경우이 코드를 저장 하는 가상 메모리 블록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe129-113">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="fe129-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe129-114">Requirements</span></span>  

<span data-ttu-id="fe129-115">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fe129-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="fe129-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fe129-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="fe129-117">**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-21-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe129-117">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-21-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fe129-118">참조</span><span class="sxs-lookup"><span data-stu-id="fe129-118">See also</span></span>

- [<span data-ttu-id="fe129-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe129-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
