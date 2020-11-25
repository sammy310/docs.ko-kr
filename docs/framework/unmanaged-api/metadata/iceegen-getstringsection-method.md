---
title: ICeeGen::GetStringSection 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
ms.openlocfilehash: bd284bced625de39791377a9248796ca3dd76f5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722923"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="9d098-102">ICeeGen::GetStringSection 메서드</span><span class="sxs-lookup"><span data-stu-id="9d098-102">ICeeGen::GetStringSection Method</span></span>

<span data-ttu-id="9d098-103">지정 된 핸들이 참조 하는 코드 섹션의 문자열 표현을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9d098-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="9d098-104">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d098-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d098-105">구문</span><span class="sxs-lookup"><span data-stu-id="9d098-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d098-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9d098-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="9d098-107">[in, out] 코드 섹션에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="9d098-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d098-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d098-108">Requirements</span></span>  

 <span data-ttu-id="9d098-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d098-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d098-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="9d098-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d098-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d098-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d098-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d098-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d098-113">참조</span><span class="sxs-lookup"><span data-stu-id="9d098-113">See also</span></span>

- [<span data-ttu-id="9d098-114">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d098-114">ICeeGen Interface</span></span>](iceegen-interface.md)
