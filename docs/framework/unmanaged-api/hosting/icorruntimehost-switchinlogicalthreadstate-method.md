---
description: '자세히 알아보기: ICorRuntimeHost:: SwitchInLogicalThreadState 메서드'
title: ICorRuntimeHost::SwitchInLogicalThreadState 메서드
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.SwitchInLogicalThreadState
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchInLogicalThreadState method [.NET Framework hosting]
- SwitchInLogicalThreadState method [.NET Framework hosting]
ms.assetid: 7df1e492-8014-43ea-80d1-a4743e9b1c17
topic_type:
- apiref
ms.openlocfilehash: 3e375379cc5d6af7c3a8fb8d64a40a389e0f9dcc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789569"
---
# <a name="icorruntimehostswitchinlogicalthreadstate-method"></a><span data-ttu-id="a82be-103">ICorRuntimeHost::SwitchInLogicalThreadState 메서드</span><span class="sxs-lookup"><span data-stu-id="a82be-103">ICorRuntimeHost::SwitchInLogicalThreadState Method</span></span>

<span data-ttu-id="a82be-104">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a82be-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a82be-105">구문</span><span class="sxs-lookup"><span data-stu-id="a82be-105">Syntax</span></span>  
  
```cpp  
HRESULT SwitchInLogicalThreadState(  
    [in] DWORD *pFiberCookie  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a82be-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a82be-106">Parameters</span></span>  

 `pFiberCookie`  
 <span data-ttu-id="a82be-107">진행 사용할 파이버를 나타내는 쿠키입니다.</span><span class="sxs-lookup"><span data-stu-id="a82be-107">[in] Cookie that indicates the fiber to use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a82be-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a82be-108">Requirements</span></span>  

 <span data-ttu-id="a82be-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a82be-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a82be-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a82be-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a82be-111">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a82be-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a82be-112">**.NET Framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="a82be-112">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a82be-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a82be-113">See also</span></span>

- [<span data-ttu-id="a82be-114">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a82be-114">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
