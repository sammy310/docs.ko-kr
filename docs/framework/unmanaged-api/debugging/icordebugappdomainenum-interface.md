---
description: '자세히 알아보기: ICorDebugAppDomainEnum 인터페이스'
title: ICorDebugAppDomainEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
ms.openlocfilehash: dfea6254e6cf4f162e44d057fb4126a67a087b61
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754162"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="0d7eb-103">ICorDebugAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d7eb-103">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="0d7eb-104">`Next` `ICorDebugAppDomainEnum` 열거형의 다음 위치에서 시작 하 여 지정 된 수의 값을 반환 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d7eb-104">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="0d7eb-105">이 인터페이스는 "ICorDebugEnum"의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="0d7eb-105">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0d7eb-106">메서드</span><span class="sxs-lookup"><span data-stu-id="0d7eb-106">Methods</span></span>  
  
|<span data-ttu-id="0d7eb-107">메서드</span><span class="sxs-lookup"><span data-stu-id="0d7eb-107">Method</span></span>|<span data-ttu-id="0d7eb-108">설명</span><span class="sxs-lookup"><span data-stu-id="0d7eb-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0d7eb-109">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="0d7eb-109">Next Method</span></span>](icordebugappdomainenum-next-method.md)|<span data-ttu-id="0d7eb-110">현재 커서 위치에서 시작 하 여 컬렉션에서 지정 된 수의 응용 프로그램 도메인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d7eb-110">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d7eb-111">설명</span><span class="sxs-lookup"><span data-stu-id="0d7eb-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d7eb-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d7eb-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d7eb-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d7eb-113">Requirements</span></span>  

 <span data-ttu-id="0d7eb-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d7eb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d7eb-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d7eb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d7eb-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d7eb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d7eb-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d7eb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7eb-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d7eb-118">See also</span></span>

- [<span data-ttu-id="0d7eb-119">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d7eb-119">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="0d7eb-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d7eb-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
