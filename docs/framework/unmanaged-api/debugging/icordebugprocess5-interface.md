---
description: '자세히 알아보기: ICorDebugProcess5 인터페이스'
title: ICorDebugProcess5 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5
helpviewer_keywords:
- ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 30a39d79-1f10-4328-9c5d-094ed824e2ba
topic_type:
- apiref
ms.openlocfilehash: 880c305c1d9786f87d9727836a973696aa686ecf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649769"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="9bcc0-103">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9bcc0-103">ICorDebugProcess5 Interface</span></span>

<span data-ttu-id="9bcc0-104">관리 되는 힙에 대 한 액세스를 지원 하 고, 관리 되는 개체의 가비지 수집에 대 한 정보를 제공 하 고, 디버거가 응용 프로그램 로컬 네이티브 이미지 캐시에서 이미지를 로드 하는지 여부를 확인 하기 위해 ICorDebugProcess 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-104">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9bcc0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-105">Methods</span></span>  
  
|<span data-ttu-id="9bcc0-106">메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-106">Method</span></span>|<span data-ttu-id="9bcc0-107">설명</span><span class="sxs-lookup"><span data-stu-id="9bcc0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9bcc0-108">EnableNGenPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-108">EnableNGenPolicy Method</span></span>](icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="9bcc0-109">응용 프로그램에서 관리 되는 디버거를 실행 하는 동안 네이티브 이미지를 로드 하는 방법을 결정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-109">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="9bcc0-110">EnumerateGCReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-110">EnumerateGCReferences Method</span></span>](icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="9bcc0-111">프로세스에서 가비지 수집 될 모든 개체에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-111">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="9bcc0-112">EnumerateHandles 메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-112">EnumerateHandles Method</span></span>](icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="9bcc0-113">프로세스의 개체 핸들에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-113">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="9bcc0-114">EnumerateHeap 메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-114">EnumerateHeap Method</span></span>](icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="9bcc0-115">관리 되는 힙의 개체에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-115">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="9bcc0-116">EnumerateHeapRegions 메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-116">EnumerateHeapRegions Method</span></span>](icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="9bcc0-117">관리 되는 힙의 영역에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-117">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="9bcc0-118">GetArrayLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-118">GetArrayLayout Method</span></span>](icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="9bcc0-119">메모리에서 배열의 레이아웃에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-119">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="9bcc0-120">GetGCHeapInformation 메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-120">GetGCHeapInformation Method</span></span>](icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="9bcc0-121">관리 되는 힙에서 가비지 수집 될 개체에 대 한 정보를 포함 하는 [COR_HEAPINFO](cor-heapinfo-structure.md) 구조체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-121">Gets a pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="9bcc0-122">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-122">GetObject Method</span></span>](icordebugprocess5-getobject-method.md)|<span data-ttu-id="9bcc0-123">관리 되는 힙의 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-123">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="9bcc0-124">GetTypeFields 메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-124">GetTypeFields Method</span></span>](icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="9bcc0-125">형식 식별자를 기반으로 하는 형식에 대 한 필드 정보가 포함 된 배열에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-125">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="9bcc0-126">GetTypeForTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-126">GetTypeForTypeID Method</span></span>](icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="9bcc0-127">해당 형식 식별자를 기반으로 하는 개체에 대 한 정보를 제공 하는 형식 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-127">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="9bcc0-128">GetTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-128">GetTypeID Method</span></span>](icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="9bcc0-129">지정 된 주소에 있는 개체의 형식 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-129">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="9bcc0-130">GetTypeLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="9bcc0-130">GetTypeLayout Method</span></span>](icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="9bcc0-131">형식 식별자를 기반으로 메모리에 있는 개체의 레이아웃에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-131">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bcc0-132">설명</span><span class="sxs-lookup"><span data-stu-id="9bcc0-132">Remarks</span></span>  

 <span data-ttu-id="9bcc0-133">이 인터페이스는 ICorDebugProcess, ICorDebugProcess2 및 [ICorDebugProcess3](icordebugprocess3-interface.md) 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-133">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9bcc0-134">이 인터페이스는 다른 컴퓨터 또는 다른 프로세스에서 원격으로 호출 되는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-134">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9bcc0-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9bcc0-135">Requirements</span></span>  

 <span data-ttu-id="9bcc0-136">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9bcc0-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bcc0-137">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9bcc0-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9bcc0-138">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9bcc0-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9bcc0-139">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9bcc0-139">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bcc0-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bcc0-140">See also</span></span>

- [<span data-ttu-id="9bcc0-141">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9bcc0-141">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="9bcc0-142">디버깅</span><span class="sxs-lookup"><span data-stu-id="9bcc0-142">Debugging</span></span>](index.md)
