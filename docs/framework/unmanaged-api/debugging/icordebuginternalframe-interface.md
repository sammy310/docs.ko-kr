---
description: '자세히 알아보기: ICorDebugInternalFrame 인터페이스'
title: ICorDebugInternalFrame 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame
helpviewer_keywords:
- ICorDebugInternalFrame interface [.NET Framework debugging]
ms.assetid: bb4772ca-0d54-4185-b738-7a6ffe9ea85a
topic_type:
- apiref
ms.openlocfilehash: 7143f270b97e10fb9664aa7f7387749ddecbbcc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791142"
---
# <a name="icordebuginternalframe-interface"></a><span data-ttu-id="791dc-103">ICorDebugInternalFrame 인터페이스</span><span class="sxs-lookup"><span data-stu-id="791dc-103">ICorDebugInternalFrame Interface</span></span>

<span data-ttu-id="791dc-104">스택의 런타임 내부 프레임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="791dc-104">Represents a runtime-internal frame on the stack.</span></span> <span data-ttu-id="791dc-105">이 인터페이스는 ICorDebugFrame 인터페이스의 하위 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="791dc-105">This interface is a subclass of the ICorDebugFrame interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="791dc-106">메서드</span><span class="sxs-lookup"><span data-stu-id="791dc-106">Methods</span></span>  
  
|<span data-ttu-id="791dc-107">메서드</span><span class="sxs-lookup"><span data-stu-id="791dc-107">Method</span></span>|<span data-ttu-id="791dc-108">설명</span><span class="sxs-lookup"><span data-stu-id="791dc-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="791dc-109">GetFrameType 메서드</span><span class="sxs-lookup"><span data-stu-id="791dc-109">GetFrameType Method</span></span>](icordebuginternalframe-getframetype-method.md)|<span data-ttu-id="791dc-110">이 내부 프레임의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="791dc-110">Gets the type of this internal frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="791dc-111">설명</span><span class="sxs-lookup"><span data-stu-id="791dc-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="791dc-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="791dc-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="791dc-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="791dc-113">Requirements</span></span>  

 <span data-ttu-id="791dc-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="791dc-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="791dc-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="791dc-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="791dc-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="791dc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="791dc-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="791dc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="791dc-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="791dc-118">See also</span></span>

- [<span data-ttu-id="791dc-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="791dc-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
