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
ms.openlocfilehash: c135c051637858682c22db58d562e1d50eea562b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723703"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="be785-102">ICLRDataTarget::SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="be785-102">ICLRDataTarget::SetThreadContext Method</span></span>

<span data-ttu-id="be785-103">대상 프로세스에서 지정 된 스레드의 현재 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="be785-103">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="be785-104">이 메서드는 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be785-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be785-105">구문</span><span class="sxs-lookup"><span data-stu-id="be785-105">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be785-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="be785-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="be785-107">진행 대상 프로세스의 스레드에 대 한 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="be785-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="be785-108">진행 컨텍스트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="be785-108">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="be785-109">진행 컨텍스트를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="be785-109">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="be785-110">버퍼의 데이터는 `context` Win32 구조의 형식이 됩니다 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="be785-110">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="be785-111">컨텍스트는 프로세서 관련 레지스터 데이터를 지정 하므로 Win32 구조의 정의는 `CONTEXT` 프로세서의 아키텍처에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="be785-111">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="be785-112">Win32 구조체의 정의는 Winnt.exe 헤더 파일을 참조 하세요 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="be785-112">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be785-113">설명</span><span class="sxs-lookup"><span data-stu-id="be785-113">Remarks</span></span>  

 <span data-ttu-id="be785-114">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="be785-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be785-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be785-115">Requirements</span></span>  

 <span data-ttu-id="be785-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be785-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be785-117">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="be785-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="be785-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be785-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be785-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be785-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be785-120">참조</span><span class="sxs-lookup"><span data-stu-id="be785-120">See also</span></span>

- [<span data-ttu-id="be785-121">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be785-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
