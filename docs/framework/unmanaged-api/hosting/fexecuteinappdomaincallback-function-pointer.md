---
description: '자세히 알아보기: FExecuteInAppDomainCallback 함수 포인터'
title: FExecuteInAppDomainCallback 함수 포인터
ms.date: 03/30/2017
api_name:
- FExecuteInAppDomainCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FExecuteInAppDomainCallback
helpviewer_keywords:
- FExecuteInAppDomainCallback function pointer [.NET Framework hosting]
ms.assetid: 2709f18f-3eee-497f-bc33-3ab7a485599b
topic_type:
- apiref
ms.openlocfilehash: 97c7fe14a3eafd6f4626d8729be3b45ad5502f1a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785396"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="2e178-103">FExecuteInAppDomainCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="2e178-103">FExecuteInAppDomainCallback Function Pointer</span></span>

<span data-ttu-id="2e178-104">관리 코드를 실행 하기 위해 CLR (공용 언어 런타임)에 의해 호출 되는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="2e178-104">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="2e178-105">이 함수 포인터는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e178-105">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e178-106">구문</span><span class="sxs-lookup"><span data-stu-id="2e178-106">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e178-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e178-107">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="2e178-108">진행 실행할 관리 코드를 포함 하는 불투명 호출자 할당 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2e178-108">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="2e178-109">이 메모리의 할당 및 수명은 호출자 (즉, CLR)에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e178-109">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="2e178-110">이는 CLR 관리 되는 힙 메모리가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2e178-110">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e178-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e178-111">Requirements</span></span>  

 <span data-ttu-id="2e178-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e178-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e178-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2e178-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e178-114">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="2e178-114">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="2e178-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e178-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e178-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e178-116">See also</span></span>

- [<span data-ttu-id="2e178-117">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="2e178-117">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
