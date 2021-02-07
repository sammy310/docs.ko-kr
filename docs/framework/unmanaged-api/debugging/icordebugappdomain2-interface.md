---
description: '자세히 알아보기: ICorDebugAppDomain2 인터페이스'
title: ICorDebugAppDomain2 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
ms.openlocfilehash: 2f2fcc4166a0c825abaa04392f9905d17e286803
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754188"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="9ddb1-103">ICorDebugAppDomain2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ddb1-103">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="9ddb1-104">배열, 포인터, 함수 포인터 및 참조 형식으로 작업 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ddb1-104">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="9ddb1-105">이 인터페이스는 ICorDebugAppDomain 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="9ddb1-105">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9ddb1-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9ddb1-106">Methods</span></span>  
  
|<span data-ttu-id="9ddb1-107">메서드</span><span class="sxs-lookup"><span data-stu-id="9ddb1-107">Method</span></span>|<span data-ttu-id="9ddb1-108">설명</span><span class="sxs-lookup"><span data-stu-id="9ddb1-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9ddb1-109">GetArrayOrPointerType 메서드</span><span class="sxs-lookup"><span data-stu-id="9ddb1-109">GetArrayOrPointerType Method</span></span>](icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="9ddb1-110">지정 된 형식의 배열 또는 지정 된 형식에 대 한 포인터 또는 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9ddb1-110">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="9ddb1-111">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="9ddb1-111">GetFunctionPointerType</span></span>](icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="9ddb1-112">지정 된 서명이 있는 함수에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9ddb1-112">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ddb1-113">설명</span><span class="sxs-lookup"><span data-stu-id="9ddb1-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9ddb1-114">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9ddb1-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ddb1-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ddb1-115">Requirements</span></span>  

 <span data-ttu-id="9ddb1-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ddb1-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ddb1-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ddb1-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ddb1-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ddb1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ddb1-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ddb1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ddb1-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ddb1-120">See also</span></span>

- [<span data-ttu-id="9ddb1-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ddb1-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
