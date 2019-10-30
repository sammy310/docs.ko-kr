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
ms.openlocfilehash: 0d34577f0f785bc851646423b8cd732ab4d1dae0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113856"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a><span data-ttu-id="a6ed0-102">ICLRDataTarget::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="a6ed0-102">ICLRDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="a6ed0-103">대상 프로세스의 지정 된 스레드에 대 한 현재 실행 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a6ed0-103">Gets the current execution context for the given thread in the target process.</span></span> <span data-ttu-id="a6ed0-104">이 메서드는 공용 언어 런타임 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6ed0-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6ed0-105">구문</span><span class="sxs-lookup"><span data-stu-id="a6ed0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]   
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6ed0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a6ed0-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="a6ed0-107">진행 대상 프로세스의 스레드에 대 한 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="a6ed0-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="a6ed0-108">진행 반환할 컨텍스트의 부분을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="a6ed0-108">[in] Flags that specify which parts of the context to return.</span></span> <span data-ttu-id="a6ed0-109">구현은 최소한 컨텍스트의 부분을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ed0-109">The implementation will return at least these parts of the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="a6ed0-110">진행 컨텍스트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a6ed0-110">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="a6ed0-111">제한이 컨텍스트를 저장할 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a6ed0-111">[out] Pointer to a buffer in which to place the context.</span></span>  
  
 <span data-ttu-id="a6ed0-112">`context` 버퍼의 데이터는 Win32 `CONTEXT` 구조 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ed0-112">The data in the `context` buffer must be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="a6ed0-113">컨텍스트는 프로세서 관련 레지스터 데이터를 지정 하므로 Win32 `CONTEXT` 구조의 정의는 프로세서의 아키텍처에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a6ed0-113">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="a6ed0-114">Win32 `CONTEXT` 구조체의 정의는 Winnt.exe 헤더 파일을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a6ed0-114">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6ed0-115">주의</span><span class="sxs-lookup"><span data-stu-id="a6ed0-115">Remarks</span></span>  
 <span data-ttu-id="a6ed0-116">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a6ed0-116">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6ed0-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6ed0-117">Requirements</span></span>  
 <span data-ttu-id="a6ed0-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6ed0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6ed0-119">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="a6ed0-119">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="a6ed0-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6ed0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6ed0-121">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6ed0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ed0-122">참조</span><span class="sxs-lookup"><span data-stu-id="a6ed0-122">See also</span></span>

- [<span data-ttu-id="a6ed0-123">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6ed0-123">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
