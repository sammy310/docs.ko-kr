---
title: ICLRDataTarget::SetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
ms.openlocfilehash: d76a907434b12b85aaedeef169390ec6f0df724a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179124"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="c8fd2-102">ICLRDataTarget::SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="c8fd2-102">ICLRDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="c8fd2-103">대상 프로세스에서 지정된 스레드의 현재 컨텍스트를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd2-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="c8fd2-104">이 메서드는 공통 언어 런타임(CLR) 데이터 액세스 서비스에서 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd2-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8fd2-105">구문</span><span class="sxs-lookup"><span data-stu-id="c8fd2-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8fd2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8fd2-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="c8fd2-107">【인】 대상 프로세스에서 스레드의 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd2-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="c8fd2-108">【인】 컨텍스트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd2-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="c8fd2-109">【인】 컨텍스트를 포함하는 버퍼에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd2-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="c8fd2-110">버퍼의 `context` 데이터는 Win32 `CONTEXT` 구조의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd2-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="c8fd2-111">컨텍스트는 프로세서별 레지스터 데이터를 지정하므로 Win32 `CONTEXT` 구조의 정의는 프로세서의 아키텍처에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd2-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="c8fd2-112">Win32 `CONTEXT` 구조의 정의에 대 한 WinNT.h 헤더 파일을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8fd2-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8fd2-113">설명</span><span class="sxs-lookup"><span data-stu-id="c8fd2-113">Remarks</span></span>  
 <span data-ttu-id="c8fd2-114">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c8fd2-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8fd2-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8fd2-115">Requirements</span></span>  
 <span data-ttu-id="c8fd2-116">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8fd2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8fd2-117">**헤더:** 클러데이터.아이들, 클러데이터.h</span><span class="sxs-lookup"><span data-stu-id="c8fd2-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c8fd2-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8fd2-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8fd2-119">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8fd2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8fd2-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8fd2-120">See also</span></span>

- [<span data-ttu-id="c8fd2-121">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8fd2-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
