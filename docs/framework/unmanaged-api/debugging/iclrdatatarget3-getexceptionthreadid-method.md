---
description: '자세히 알아보기: ICLRDataTarget3:: GetExceptionThreadID 메서드'
title: ICLRDataTarget3::GetExceptionThreadID 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
ms.openlocfilehash: 8202b6d83d0c81853111c5da7cfb8deec4d4e222
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794821"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="4c28c-103">ICLRDataTarget3::GetExceptionThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="4c28c-103">ICLRDataTarget3::GetExceptionThreadID Method</span></span>

<span data-ttu-id="4c28c-104">CLR(공용 언어 런타임) 데이터 액세스 서비스에 의해 호출되어 예외를 throw한 스레드의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4c28c-104">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c28c-105">구문</span><span class="sxs-lookup"><span data-stu-id="4c28c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c28c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4c28c-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="4c28c-107">[out] 예외를 throw한 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4c28c-107">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c28c-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="4c28c-108">Return Value</span></span>  

 <span data-ttu-id="4c28c-109">반환 값은 성공 시 `S_OK`이고 실패 시에는 오류 `HRESULT` 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4c28c-109">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="4c28c-110">`HRESULT` 코드는 다음을 비롯한 여러 항목을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c28c-110">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="4c28c-111">반환 코드</span><span class="sxs-lookup"><span data-stu-id="4c28c-111">Return code</span></span>|<span data-ttu-id="4c28c-112">설명</span><span class="sxs-lookup"><span data-stu-id="4c28c-112">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="4c28c-113">메서드가 정상적으로 실행되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4c28c-113">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="4c28c-114">예외의 유효한 스레드 ID를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c28c-114">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c28c-115">설명</span><span class="sxs-lookup"><span data-stu-id="4c28c-115">Remarks</span></span>  

 <span data-ttu-id="4c28c-116">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4c28c-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c28c-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4c28c-117">Requirements</span></span>  

 <span data-ttu-id="4c28c-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4c28c-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c28c-119">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="4c28c-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4c28c-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c28c-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c28c-121">**.NET Framework 버전:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4c28c-121">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c28c-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4c28c-122">See also</span></span>

- [<span data-ttu-id="4c28c-123">ICLRDataTarget3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4c28c-123">ICLRDataTarget3 Interface</span></span>](iclrdatatarget3-interface.md)
- [<span data-ttu-id="4c28c-124">GetExceptionContextRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="4c28c-124">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="4c28c-125">GetExceptionRecord 메서드</span><span class="sxs-lookup"><span data-stu-id="4c28c-125">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)
