---
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
ms.openlocfilehash: 5c0fb023dd355f3a9c1ed846913f86b354592ed5
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860609"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="c8028-102">ICLRDataTarget::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="c8028-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="c8028-103">대상 프로세스의 지정 된 스레드에 대 한 현재 실행 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8028-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="c8028-104">이 메서드는 공용 언어 런타임 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8028-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8028-105">구문</span><span class="sxs-lookup"><span data-stu-id="c8028-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8028-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8028-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="c8028-107">진행 대상 프로세스의 스레드에 대 한 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c8028-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="c8028-108">진행 반환할 컨텍스트의 부분을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="c8028-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="c8028-109">구현은 최소한 컨텍스트의 부분을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8028-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c8028-110">진행 컨텍스트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c8028-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="c8028-111">제한이 컨텍스트를 저장할 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c8028-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="c8028-112">`context` 버퍼의 데이터는 Win32 `CONTEXT` 구조의 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8028-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="c8028-113">컨텍스트는 프로세서 관련 레지스터 데이터를 지정 하므로 Win32 `CONTEXT` 구조의 정의는 프로세서의 아키텍처에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c8028-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="c8028-114">Win32 `CONTEXT` 구조체의 정의는 winnt.exe 헤더 파일을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8028-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8028-115">설명</span><span class="sxs-lookup"><span data-stu-id="c8028-115">Remarks</span></span>  
 <span data-ttu-id="c8028-116">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c8028-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8028-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8028-117">Requirements</span></span>  
 <span data-ttu-id="c8028-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8028-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8028-119">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="c8028-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c8028-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8028-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8028-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8028-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8028-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8028-122">See also</span></span>

- [<span data-ttu-id="c8028-123">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8028-123">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
