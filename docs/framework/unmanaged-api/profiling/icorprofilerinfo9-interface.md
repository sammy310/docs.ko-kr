---
description: '자세히 알아보기: ICorProfilerInfo9 인터페이스'
title: ICorProfilerInfo9 인터페이스
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 954cb16d2b789359693f6a8fa3e0f6e19ad19b3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736910"
---
# <a name="icorprofilerinfo9-interface"></a><span data-ttu-id="f941a-103">ICorProfilerInfo9 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f941a-103">ICorProfilerInfo9 Interface</span></span>

<span data-ttu-id="f941a-104">여러 네이티브 코드 버전이 있는 함수에 대 한 정보를 쿼리 하는 메서드를 제공 하는 [ICorProfilerInfo8](icorprofilerinfo8-interface.md) 의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f941a-104">A subclass of [ICorProfilerInfo8](icorprofilerinfo8-interface.md) that provides methods to query information about functions with multiple native code versions.</span></span>  

## <a name="methods"></a><span data-ttu-id="f941a-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f941a-105">Methods</span></span>  

| <span data-ttu-id="f941a-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f941a-106">Method</span></span>|<span data-ttu-id="f941a-107">설명</span><span class="sxs-lookup"><span data-stu-id="f941a-107">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="f941a-108">GetNativeCodeStartAddresses 메서드</span><span class="sxs-lookup"><span data-stu-id="f941a-108">GetNativeCodeStartAddresses Method</span></span>](icorprofilerinfo9-getnativecodestartaddresses-method.md)| <span data-ttu-id="f941a-109">FunctionId 및 rejitId가 지정 된 경우 현재 존재 하는이 코드의 모든 jit 컴파일된 버전의 네이티브 코드 시작 주소를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f941a-109">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span> |
|[<span data-ttu-id="f941a-110">GetILToNativeMapping3 메서드</span><span class="sxs-lookup"><span data-stu-id="f941a-110">GetILToNativeMapping3 Method</span></span>](icorprofilerinfo9-getiltonativemapping3-method.md)| <span data-ttu-id="f941a-111">네이티브 코드 시작 주소가 지정 된 경우이 jit 컴파일된 버전의 코드에 대 한 네이티브 IL 매핑 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f941a-111">Given the native code start address, returns the native to IL mapping information for this jitted version of the code.</span></span> |
|[<span data-ttu-id="f941a-112">GetCodeInfo4 메서드</span><span class="sxs-lookup"><span data-stu-id="f941a-112">GetCodeInfo4 Method</span></span>](icorprofilerinfo9-getcodeinfo4-method.md)| <span data-ttu-id="f941a-113">네이티브 코드 시작 주소가 지정 된 경우이 코드를 저장 하는 가상 메모리 블록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f941a-113">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span> |

## <a name="requirements"></a><span data-ttu-id="f941a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f941a-114">Requirements</span></span>  

<span data-ttu-id="f941a-115">**플랫폼:** [.Net Core 지원 운영 체제](../../../core/install/windows.md?pivots=os-windows)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f941a-115">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>  
<span data-ttu-id="f941a-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f941a-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="f941a-117">**.Net 버전:**[!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f941a-117">**.NET Versions:** [!INCLUDE[net_core](../../../../includes/net-core-22-md.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="f941a-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f941a-118">See also</span></span>

- [<span data-ttu-id="f941a-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f941a-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
