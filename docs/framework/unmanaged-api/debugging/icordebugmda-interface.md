---
description: '자세히 알아보기: ICorDebugMDA 인터페이스'
title: ICorDebugMDA 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugMDA
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA
helpviewer_keywords:
- ICorDebugMDA interface [.NET Framework debugging]
ms.assetid: 8ecbb854-295c-4dd4-b9fc-01ebeac46e06
topic_type:
- apiref
ms.openlocfilehash: 8e6e779c58d71b07edc9b63dff72aef728ebe050
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801126"
---
# <a name="icordebugmda-interface"></a><span data-ttu-id="62d8e-103">ICorDebugMDA 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62d8e-103">ICorDebugMDA Interface</span></span>

<span data-ttu-id="62d8e-104">MDA(관리 디버깅 도우미) 메시지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="62d8e-104">Represents a managed debugging assistant (MDA) message.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62d8e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="62d8e-105">Methods</span></span>  
  
|<span data-ttu-id="62d8e-106">메서드</span><span class="sxs-lookup"><span data-stu-id="62d8e-106">Method</span></span>|<span data-ttu-id="62d8e-107">설명</span><span class="sxs-lookup"><span data-stu-id="62d8e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62d8e-108">GetDescription 메서드</span><span class="sxs-lookup"><span data-stu-id="62d8e-108">GetDescription Method</span></span>](icordebugmda-getdescription-method.md)|<span data-ttu-id="62d8e-109">이 MDA에 대 한 설명을 포함 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="62d8e-109">Gets a string containing a description of this MDA.</span></span>|  
|[<span data-ttu-id="62d8e-110">GetFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="62d8e-110">GetFlags Method</span></span>](icordebugmda-getflags-method.md)|<span data-ttu-id="62d8e-111">이 MDA와 연결 된 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="62d8e-111">Gets the flags associated with this MDA.</span></span>|  
|[<span data-ttu-id="62d8e-112">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="62d8e-112">GetName Method</span></span>](icordebugmda-getname-method.md)|<span data-ttu-id="62d8e-113">이 MDA의 이름을 포함 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="62d8e-113">Gets a string containing the name of this MDA.</span></span>|  
|[<span data-ttu-id="62d8e-114">GetOSThreadId 메서드</span><span class="sxs-lookup"><span data-stu-id="62d8e-114">GetOSThreadId Method</span></span>](icordebugmda-getosthreadid-method.md)|<span data-ttu-id="62d8e-115">이 MDA가 실행 되 고 있는 운영 체제 스레드 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="62d8e-115">Gets the operating system thread identifier upon which this MDA is executing.</span></span>|  
|[<span data-ttu-id="62d8e-116">GetXML 메서드</span><span class="sxs-lookup"><span data-stu-id="62d8e-116">GetXML Method</span></span>](icordebugmda-getxml-method.md)|<span data-ttu-id="62d8e-117">이 MDA와 연결 된 전체 XML 스트림을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="62d8e-117">Gets the full XML stream associated with this MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62d8e-118">설명</span><span class="sxs-lookup"><span data-stu-id="62d8e-118">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62d8e-119">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="62d8e-119">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62d8e-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62d8e-120">Requirements</span></span>  

 <span data-ttu-id="62d8e-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62d8e-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62d8e-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62d8e-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62d8e-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62d8e-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62d8e-124">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62d8e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62d8e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62d8e-125">See also</span></span>

- [<span data-ttu-id="62d8e-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62d8e-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="62d8e-127">관리 디버깅 도우미를 사용하여 오류 진단</span><span class="sxs-lookup"><span data-stu-id="62d8e-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
