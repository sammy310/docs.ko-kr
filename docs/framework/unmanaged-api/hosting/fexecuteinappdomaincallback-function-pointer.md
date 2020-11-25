---
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
ms.openlocfilehash: 8b9c6bb41b7438b9764ac2a8a7fc1677bc08557a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733687"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="dc925-102">FExecuteInAppDomainCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="dc925-102">FExecuteInAppDomainCallback Function Pointer</span></span>

<span data-ttu-id="dc925-103">관리 코드를 실행 하기 위해 CLR (공용 언어 런타임)에 의해 호출 되는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="dc925-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="dc925-104">이 함수 포인터는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc925-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc925-105">구문</span><span class="sxs-lookup"><span data-stu-id="dc925-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc925-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc925-106">Parameters</span></span>  

 `cookie`  
 <span data-ttu-id="dc925-107">진행 실행할 관리 코드를 포함 하는 불투명 호출자 할당 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc925-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="dc925-108">이 메모리의 할당 및 수명은 호출자 (즉, CLR)에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc925-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="dc925-109">이는 CLR 관리 되는 힙 메모리가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="dc925-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc925-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc925-110">Requirements</span></span>  

 <span data-ttu-id="dc925-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc925-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc925-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="dc925-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dc925-113">**라이브러리:** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="dc925-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="dc925-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc925-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc925-115">참조</span><span class="sxs-lookup"><span data-stu-id="dc925-115">See also</span></span>

- [<span data-ttu-id="dc925-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="dc925-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
