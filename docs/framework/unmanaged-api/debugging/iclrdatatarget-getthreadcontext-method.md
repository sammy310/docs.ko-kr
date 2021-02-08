---
description: '자세히 알아보기: ICLRDataTarget:: GetThreadContext 메서드'
title: ICLRDataTarget::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 210f4294aed31307557db419a0fb567cc71d4354
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785694"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="ab56d-103">ICLRDataTarget::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="ab56d-103">ICLRDataTarget::GetThreadContext Method</span></span>

<span data-ttu-id="ab56d-104">대상 프로세스의 지정 된 스레드에 대 한 현재 실행 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ab56d-104">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="ab56d-105">이 메서드는 공용 언어 런타임 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab56d-105">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab56d-106">구문</span><span class="sxs-lookup"><span data-stu-id="ab56d-106">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab56d-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab56d-107">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="ab56d-108">진행 대상 프로세스의 스레드에 대 한 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="ab56d-108">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="ab56d-109">진행 반환할 컨텍스트의 부분을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="ab56d-109">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="ab56d-110">구현은 최소한 컨텍스트의 부분을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab56d-110">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="ab56d-111">진행 컨텍스트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ab56d-111">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="ab56d-112">제한이 컨텍스트를 저장할 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ab56d-112">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="ab56d-113">버퍼의 데이터는 `context` Win32 구조의 형식 이어야 합니다 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="ab56d-113">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="ab56d-114">컨텍스트는 프로세서 관련 레지스터 데이터를 지정 하므로 Win32 구조의 정의는 `CONTEXT` 프로세서의 아키텍처에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="ab56d-114">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="ab56d-115">Win32 구조체의 정의는 Winnt.exe 헤더 파일을 참조 하세요 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="ab56d-115">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab56d-116">설명</span><span class="sxs-lookup"><span data-stu-id="ab56d-116">Remarks</span></span>  

 <span data-ttu-id="ab56d-117">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ab56d-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab56d-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab56d-118">Requirements</span></span>  

 <span data-ttu-id="ab56d-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab56d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab56d-120">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="ab56d-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ab56d-121">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab56d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab56d-122">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab56d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab56d-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab56d-123">See also</span></span>

- [<span data-ttu-id="ab56d-124">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab56d-124">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
