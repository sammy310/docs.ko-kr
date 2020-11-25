---
title: ICorDebugAppDomain3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
ms.openlocfilehash: 644457edbf5035f6d946e1c83ff0053fb118288e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698236"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="0670e-102">ICorDebugAppDomain3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0670e-102">ICorDebugAppDomain3 Interface</span></span>

<span data-ttu-id="0670e-103">응용 프로그램 도메인에 현재 로드 된 Windows 런타임 형식의 관리 되는 표현에 대 한 정보를 검색 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0670e-103">Provides methods to retrieve information about the managed representations of Windows Runtime types currently loaded in an application domain.</span></span> <span data-ttu-id="0670e-104">이 인터페이스는 ICorDebugAppDomain 및 ICorDebugAppDomain2 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="0670e-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0670e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0670e-105">Methods</span></span>  
  
|<span data-ttu-id="0670e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="0670e-106">Method</span></span>|<span data-ttu-id="0670e-107">설명</span><span class="sxs-lookup"><span data-stu-id="0670e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0670e-108">ICorDebugAppDomain3:: GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="0670e-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="0670e-109">모든 캐시 된 Windows 런타임 형식에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0670e-109">Gets an enumerator for all cached Windows Runtime types.</span></span>|  
|[<span data-ttu-id="0670e-110">ICorDebugAppDomain3:: GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="0670e-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="0670e-111">인터페이스 식별자를 기반으로 응용 프로그램 도메인의 캐시 된 Windows 런타임 형식에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0670e-111">Gets an enumerator for cached Windows Runtime types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0670e-112">설명</span><span class="sxs-lookup"><span data-stu-id="0670e-112">Remarks</span></span>  

 <span data-ttu-id="0670e-113">이 인터페이스는 디버거에서의 함수 계산 호출과 함께 사용 됩니다 `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)` .</span><span class="sxs-lookup"><span data-stu-id="0670e-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="0670e-114">메서드가 Windows 런타임 서버 개체에서 지 원하는 인터페이스 식별자를 검색 하는 경우 디버거는이 인터페이스에 정의 된 메서드를 사용 하 여 해당 인터페이스에 해당 하는 관리 되는 형식에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0670e-114">When the method retrieves the interface identifiers supported by a Windows Runtime server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="0670e-115">이 인터페이스의 인스턴스를 검색 하려면 `QueryInterface` ICorDebugAppDomain 또는 ICorDebugAppDomain2 인터페이스의 인스턴스에서를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0670e-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0670e-116">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0670e-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0670e-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0670e-117">Requirements</span></span>  

 <span data-ttu-id="0670e-118">**플랫폼:** Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="0670e-118">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="0670e-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0670e-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0670e-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0670e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0670e-121">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0670e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0670e-122">참조</span><span class="sxs-lookup"><span data-stu-id="0670e-122">See also</span></span>

- [<span data-ttu-id="0670e-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0670e-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
