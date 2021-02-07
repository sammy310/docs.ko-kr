---
description: '자세히 알아보기: ICLRDataTarget:: SetThreadContext 메서드'
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
ms.openlocfilehash: fc428bc887f7ba10f3096cdf17a757fb252418f0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738206"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a><span data-ttu-id="0f359-103">ICLRDataTarget::SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="0f359-103">ICLRDataTarget::SetThreadContext Method</span></span>

<span data-ttu-id="0f359-104">대상 프로세스에서 지정 된 스레드의 현재 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f359-104">Sets the current context of the specified thread in the target process.</span></span> <span data-ttu-id="0f359-105">이 메서드는 CLR (공용 언어 런타임) 데이터 액세스 서비스에 의해 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f359-105">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f359-106">구문</span><span class="sxs-lookup"><span data-stu-id="0f359-106">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f359-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0f359-107">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="0f359-108">진행 대상 프로세스의 스레드에 대 한 운영 체제 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="0f359-108">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="0f359-109">진행 컨텍스트의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0f359-109">[in] The size of the context.</span></span>  
  
 `context`  
 <span data-ttu-id="0f359-110">진행 컨텍스트를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0f359-110">[in] Pointer to a buffer containing the context.</span></span>  
  
 <span data-ttu-id="0f359-111">버퍼의 데이터는 `context` Win32 구조의 형식이 됩니다 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="0f359-111">The data in the `context` buffer will be in the format of the Win32 `CONTEXT` structure.</span></span> <span data-ttu-id="0f359-112">컨텍스트는 프로세서 관련 레지스터 데이터를 지정 하므로 Win32 구조의 정의는 `CONTEXT` 프로세서의 아키텍처에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0f359-112">The context specifies processor-specific register data, so the definition of the Win32 `CONTEXT` structure depends on the processor's architecture.</span></span> <span data-ttu-id="0f359-113">Win32 구조체의 정의는 Winnt.exe 헤더 파일을 참조 하세요 `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="0f359-113">Refer to the WinNT.h header file for the definition of the Win32 `CONTEXT` structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f359-114">설명</span><span class="sxs-lookup"><span data-stu-id="0f359-114">Remarks</span></span>  

 <span data-ttu-id="0f359-115">이 메서드는 디버깅 애플리케이션의 작성자가 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0f359-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f359-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f359-116">Requirements</span></span>  

 <span data-ttu-id="0f359-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f359-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f359-118">**헤더:** ClrData .idl, ClrData .h</span><span class="sxs-lookup"><span data-stu-id="0f359-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="0f359-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f359-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f359-120">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f359-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f359-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0f359-121">See also</span></span>

- [<span data-ttu-id="0f359-122">ICLRDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f359-122">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
