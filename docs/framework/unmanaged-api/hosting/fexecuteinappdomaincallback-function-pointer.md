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
ms.openlocfilehash: 6fd7a19d9fc77b43bbceb1b5e5399a455429e700
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616153"
---
# <a name="fexecuteinappdomaincallback-function-pointer"></a><span data-ttu-id="f0fa3-102">FExecuteInAppDomainCallback 함수 포인터</span><span class="sxs-lookup"><span data-stu-id="f0fa3-102">FExecuteInAppDomainCallback Function Pointer</span></span>
<span data-ttu-id="f0fa3-103">관리 코드를 실행 하기 위해 CLR (공용 언어 런타임)에 의해 호출 되는 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="f0fa3-103">Points to a function that is called by the common language runtime (CLR) to execute managed code.</span></span>  
  
 <span data-ttu-id="f0fa3-104">이 함수 포인터는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0fa3-104">This function pointer has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0fa3-105">구문</span><span class="sxs-lookup"><span data-stu-id="f0fa3-105">Syntax</span></span>  
  
```cpp  
typedef HRESULT (__stdcall *FExecuteInAppDomainCallback) (  
    [in] void  *cookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0fa3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0fa3-106">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="f0fa3-107">진행 실행할 관리 코드를 포함 하는 불투명 호출자 할당 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f0fa3-107">[in] A pointer to opaque caller-allocated memory that contains the managed code to be executed.</span></span>  
  
 <span data-ttu-id="f0fa3-108">이 메모리의 할당 및 수명은 호출자 (즉, CLR)에 의해 제어 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0fa3-108">The allocation and lifetime of this memory are controlled by the caller (that is, the CLR).</span></span> <span data-ttu-id="f0fa3-109">이는 CLR 관리 되는 힙 메모리가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f0fa3-109">This is not CLR managed-heap memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0fa3-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0fa3-110">Requirements</span></span>  
 <span data-ttu-id="f0fa3-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0fa3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0fa3-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f0fa3-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0fa3-113">**라이브러리:** Mscorwks.dll</span><span class="sxs-lookup"><span data-stu-id="f0fa3-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="f0fa3-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0fa3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0fa3-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0fa3-115">See also</span></span>

- [<span data-ttu-id="f0fa3-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="f0fa3-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
