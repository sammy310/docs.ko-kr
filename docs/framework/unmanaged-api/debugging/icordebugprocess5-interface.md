---
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
ms.openlocfilehash: cef69ac7e3572b67dd676ce8408e4210d93accf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717580"
---
# <a name="icordebugprocess5-interface"></a><span data-ttu-id="c076f-102">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c076f-102">ICorDebugProcess5 Interface</span></span>

<span data-ttu-id="c076f-103">관리 되는 힙에 대 한 액세스를 지원 하 고, 관리 되는 개체의 가비지 수집에 대 한 정보를 제공 하 고, 디버거가 응용 프로그램 로컬 네이티브 이미지 캐시에서 이미지를 로드 하는지 여부를 확인 하기 위해 ICorDebugProcess 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-103">Extends the ICorDebugProcess interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application local native image cache.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c076f-104">메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-104">Methods</span></span>  
  
|<span data-ttu-id="c076f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-105">Method</span></span>|<span data-ttu-id="c076f-106">설명</span><span class="sxs-lookup"><span data-stu-id="c076f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c076f-107">EnableNGenPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-107">EnableNGenPolicy Method</span></span>](icordebugprocess5-enablengenpolicy-method.md)|<span data-ttu-id="c076f-108">응용 프로그램에서 관리 되는 디버거를 실행 하는 동안 네이티브 이미지를 로드 하는 방법을 결정 하는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-108">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>|  
|[<span data-ttu-id="c076f-109">EnumerateGCReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-109">EnumerateGCReferences Method</span></span>](icordebugprocess5-enumerategcreferences-method.md)|<span data-ttu-id="c076f-110">프로세스에서 가비지 수집 될 모든 개체에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-110">Gets an enumerator for all objects that are to be garbage-collected in a process.</span></span>|  
|[<span data-ttu-id="c076f-111">EnumerateHandles 메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-111">EnumerateHandles Method</span></span>](icordebugprocess5-enumeratehandles-method.md)|<span data-ttu-id="c076f-112">프로세스의 개체 핸들에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-112">Gets an enumerator for object handles in a process.</span></span>|  
|[<span data-ttu-id="c076f-113">EnumerateHeap 메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-113">EnumerateHeap Method</span></span>](icordebugprocess5-enumerateheap-method.md)|<span data-ttu-id="c076f-114">관리 되는 힙의 개체에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-114">Gets an enumerator for objects on the managed heap.</span></span>|  
|[<span data-ttu-id="c076f-115">EnumerateHeapRegions 메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-115">EnumerateHeapRegions Method</span></span>](icordebugprocess5-enumerateheapregions-method.md)|<span data-ttu-id="c076f-116">관리 되는 힙의 영역에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-116">Gets an enumerator for regions of the managed heap.</span></span>|  
|[<span data-ttu-id="c076f-117">GetArrayLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-117">GetArrayLayout Method</span></span>](icordebugprocess5-getarraylayout-method.md)|<span data-ttu-id="c076f-118">메모리에서 배열의 레이아웃에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-118">Gets information about the layout of an array in memory.</span></span>|  
|[<span data-ttu-id="c076f-119">GetGCHeapInformation 메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-119">GetGCHeapInformation Method</span></span>](icordebugprocess5-getgcheapinformation-method.md)|<span data-ttu-id="c076f-120">관리 되는 힙에서 가비지 수집 될 개체에 대 한 정보를 포함 하는 [COR_HEAPINFO](cor-heapinfo-structure.md) 구조체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-120">Gets a pointer to a [COR_HEAPINFO](cor-heapinfo-structure.md) structure that contains information about objects that are to be garbage-collected on the managed heap.</span></span>|  
|[<span data-ttu-id="c076f-121">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-121">GetObject Method</span></span>](icordebugprocess5-getobject-method.md)|<span data-ttu-id="c076f-122">관리 되는 힙의 개체에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-122">Gets a pointer to an object on the managed heap.</span></span>|  
|[<span data-ttu-id="c076f-123">GetTypeFields 메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-123">GetTypeFields Method</span></span>](icordebugprocess5-gettypefields-method.md)|<span data-ttu-id="c076f-124">형식 식별자를 기반으로 하는 형식에 대 한 필드 정보가 포함 된 배열에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-124">Gets a pointer to an array that contains field information for a type based on its type identifier.</span></span>|  
|[<span data-ttu-id="c076f-125">GetTypeForTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-125">GetTypeForTypeID Method</span></span>](icordebugprocess5-gettypefortypeid-method.md)|<span data-ttu-id="c076f-126">해당 형식 식별자를 기반으로 하는 개체에 대 한 정보를 제공 하는 형식 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-126">Gets a type object that provides information about an object based on its type identifiers.</span></span>|  
|[<span data-ttu-id="c076f-127">GetTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-127">GetTypeID Method</span></span>](icordebugprocess5-gettypeid-method.md)|<span data-ttu-id="c076f-128">지정 된 주소에 있는 개체의 형식 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-128">Gets the type identifier for the object at a specified address.</span></span>|  
|[<span data-ttu-id="c076f-129">GetTypeLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="c076f-129">GetTypeLayout Method</span></span>](icordebugprocess5-gettypelayout-method.md)|<span data-ttu-id="c076f-130">형식 식별자를 기반으로 메모리에 있는 개체의 레이아웃에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-130">Gets information about the layout of an object in memory based on its type identifier.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c076f-131">설명</span><span class="sxs-lookup"><span data-stu-id="c076f-131">Remarks</span></span>  

 <span data-ttu-id="c076f-132">이 인터페이스는 ICorDebugProcess, ICorDebugProcess2 및 [ICorDebugProcess3](icordebugprocess3-interface.md) 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-132">This interface logically extends the ICorDebugProcess, ICorDebugProcess2, and [ICorDebugProcess3](icordebugprocess3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c076f-133">이 인터페이스는 다른 컴퓨터 또는 다른 프로세스에서 원격으로 호출 되는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c076f-133">This interface does not support being called remotely, either from another machine or from another process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c076f-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c076f-134">Requirements</span></span>  

 <span data-ttu-id="c076f-135">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c076f-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c076f-136">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c076f-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c076f-137">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c076f-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c076f-138">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c076f-138">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c076f-139">참조</span><span class="sxs-lookup"><span data-stu-id="c076f-139">See also</span></span>

- [<span data-ttu-id="c076f-140">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c076f-140">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c076f-141">디버깅</span><span class="sxs-lookup"><span data-stu-id="c076f-141">Debugging</span></span>](index.md)
