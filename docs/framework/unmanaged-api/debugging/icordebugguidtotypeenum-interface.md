---
description: '자세히 알아보기: ICorDebugGuidToTypeEnum 인터페이스'
title: ICorDebugGuidToTypeEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
ms.openlocfilehash: abcdc9537f6f6ff2e0ac9b2be86734efbf303493
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660988"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="87b24-103">ICorDebugGuidToTypeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87b24-103">ICorDebugGuidToTypeEnum Interface</span></span>

<span data-ttu-id="87b24-104">ICorDebugType 인스턴스로 표시 되는 Guid 집합과 해당 형식 간의 매핑을 정의 하는 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b24-104">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="87b24-105">이 인터페이스는 ICorDebugEnum 인터페이스의 메서드를 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="87b24-105">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87b24-106">메서드</span><span class="sxs-lookup"><span data-stu-id="87b24-106">Methods</span></span>  
  
|<span data-ttu-id="87b24-107">메서드</span><span class="sxs-lookup"><span data-stu-id="87b24-107">Method</span></span>|<span data-ttu-id="87b24-108">설명</span><span class="sxs-lookup"><span data-stu-id="87b24-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87b24-109">ICorDebugGuidToTypeEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="87b24-109">ICorDebugGuidToTypeEnum::Next</span></span>](icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="87b24-110">Guid를 형식 정보에 매핑하는 지정 된 수의 [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87b24-110">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87b24-111">설명</span><span class="sxs-lookup"><span data-stu-id="87b24-111">Remarks</span></span>  

 <span data-ttu-id="87b24-112">`ICorDebugGuidToTypeEnum`인터페이스 개체는 [ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) 메서드를 호출 하 여 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b24-112">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="87b24-113">디버거는이 인터페이스의 [다음](icordebugguidtotypeenum-next-method.md) 메서드를 호출 하 여 [ICorDebugAppDomain3:: GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) 메서드 호출에 사용 되는 응용 프로그램 도메인에 로드 된 Windows 런타임 형식의 관리 되는 표현에 대 한 매핑을 나타내는 [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) 개체를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87b24-113">A debugger can call this interface's [Next](icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87b24-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87b24-114">Requirements</span></span>  

 <span data-ttu-id="87b24-115">**플랫폼:** Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="87b24-115">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="87b24-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="87b24-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="87b24-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87b24-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87b24-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87b24-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87b24-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87b24-119">See also</span></span>

- [<span data-ttu-id="87b24-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87b24-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
