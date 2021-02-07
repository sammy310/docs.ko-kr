---
description: ICorDebugProcess6::D ecodeEvent 메서드에 대해 자세히 알아보세요.
title: ICorDebugProcess6::DecodeEvent 메서드
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: 241b24335f96a250156effde34683c8f32a47e3f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746219"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="31428-103">ICorDebugProcess6::DecodeEvent 메서드</span><span class="sxs-lookup"><span data-stu-id="31428-103">ICorDebugProcess6::DecodeEvent Method</span></span>

<span data-ttu-id="31428-104">특수하게 작성된 네이티브 예외 디버그 이벤트의 페이로드에서 캡슐화된 관리되는 디버그 이벤트를 디코딩합니다.</span><span class="sxs-lookup"><span data-stu-id="31428-104">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31428-105">구문</span><span class="sxs-lookup"><span data-stu-id="31428-105">Syntax</span></span>  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,
        [in] DWORD dwThreadId,
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31428-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="31428-106">Parameters</span></span>  

 `pRecord`  
 <span data-ttu-id="31428-107">[in] 관리되는 디버그 이벤트에 대한 정보를 포함하는 네이티브 예외 디버그 이벤트의 바이트 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="31428-107">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="31428-108">[in] `pRecord` 바이트 배열의 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="31428-108">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="31428-109">진행 관리 되지 않는 디버그 이벤트의 형식을 지정 하는 [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) 열거형 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="31428-109">[in] A [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="31428-110">[in] 대상 아키텍처를 사용하며 디버그 이벤트에 대한 추가 정보를 지정하는 비트 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="31428-110">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="31428-111">Windows 시스템의 경우 [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) 열거의 멤버일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31428-111">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="31428-112">[in] 예외가 throw된 스레드의 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="31428-112">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="31428-113">제한이 디코딩된 관리 되는 디버그 이벤트를 나타내는 [ICorDebugDebugEvent](icordebugdebugevent-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="31428-113">[out] A pointer to the address of an [ICorDebugDebugEvent](icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31428-114">설명</span><span class="sxs-lookup"><span data-stu-id="31428-114">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="31428-115">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31428-115">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31428-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="31428-116">Requirements</span></span>  

 <span data-ttu-id="31428-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31428-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31428-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31428-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31428-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31428-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31428-120">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31428-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31428-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31428-121">See also</span></span>

- [<span data-ttu-id="31428-122">ICorDebugProcess6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31428-122">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="31428-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31428-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
