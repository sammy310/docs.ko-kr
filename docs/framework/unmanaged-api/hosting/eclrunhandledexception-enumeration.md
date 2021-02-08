---
description: '자세히 알아보기: EClrUnhandledException 열거형'
title: EClrUnhandledException 열거형
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
ms.openlocfilehash: 088d448a92c4d9030208537b9c788477c85f9d37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785551"
---
# <a name="eclrunhandledexception-enumeration"></a><span data-ttu-id="b1fa8-103">EClrUnhandledException 열거형</span><span class="sxs-lookup"><span data-stu-id="b1fa8-103">EClrUnhandledException Enumeration</span></span>

<span data-ttu-id="b1fa8-104">사용자 코드에서 처리 되지 않은 예외를 관리 하는 데 사용할 수 있는 옵션을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1fa8-104">Describes the available options for managing exceptions that are unhandled in user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1fa8-105">구문</span><span class="sxs-lookup"><span data-stu-id="b1fa8-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a><span data-ttu-id="b1fa8-106">구성원</span><span class="sxs-lookup"><span data-stu-id="b1fa8-106">Members</span></span>  
  
|<span data-ttu-id="b1fa8-107">멤버</span><span class="sxs-lookup"><span data-stu-id="b1fa8-107">Member</span></span>|<span data-ttu-id="b1fa8-108">설명</span><span class="sxs-lookup"><span data-stu-id="b1fa8-108">Description</span></span>|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|<span data-ttu-id="b1fa8-109">기본 동작이 발생 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1fa8-109">Specifies that the default behavior occurs.</span></span> <span data-ttu-id="b1fa8-110">프로세스가 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1fa8-110">The process is torn down.</span></span>|  
|`eHostDeterminedPolicy`|<span data-ttu-id="b1fa8-111">CLR (공용 언어 런타임)이 처리 되지 않은 예외를 무시 하 고 호스트에서 추가 작업을 확인할 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1fa8-111">Specifies that the common language runtime (CLR) ignores unhandled exceptions and lets the host determine any further action.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1fa8-112">설명</span><span class="sxs-lookup"><span data-stu-id="b1fa8-112">Remarks</span></span>  

 <span data-ttu-id="b1fa8-113">CLR이 이전 버전과 동일 하 게 동작 하도록 지정 하려면 멤버를 사용 `eHostDeterminedPolicy` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1fa8-113">To specify that the CLR behave like earlier versions, use the `eHostDeterminedPolicy` member.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1fa8-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1fa8-114">Requirements</span></span>  

 <span data-ttu-id="b1fa8-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1fa8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1fa8-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="b1fa8-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b1fa8-117">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b1fa8-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1fa8-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1fa8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1fa8-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b1fa8-119">See also</span></span>

- [<span data-ttu-id="b1fa8-120">EClrFailure 열거형</span><span class="sxs-lookup"><span data-stu-id="b1fa8-120">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="b1fa8-121">EClrOperation 열거형</span><span class="sxs-lookup"><span data-stu-id="b1fa8-121">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="b1fa8-122">ICLRPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1fa8-122">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="b1fa8-123">SetUnhandledExceptionPolicy 메서드</span><span class="sxs-lookup"><span data-stu-id="b1fa8-123">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [<span data-ttu-id="b1fa8-124">IHostPolicyManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1fa8-124">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
- [<span data-ttu-id="b1fa8-125">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="b1fa8-125">Hosting Enumerations</span></span>](hosting-enumerations.md)
