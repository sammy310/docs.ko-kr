---
title: ICeeGen::EmitString 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
ms.openlocfilehash: b9c907868df31da8d995c6a6b86db258d395335d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715448"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="ad3e8-102">ICeeGen::EmitString 메서드</span><span class="sxs-lookup"><span data-stu-id="ad3e8-102">ICeeGen::EmitString Method</span></span>

<span data-ttu-id="ad3e8-103">지정 된 문자열을 코드 베이스에 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="ad3e8-104">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad3e8-105">구문</span><span class="sxs-lookup"><span data-stu-id="ad3e8-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad3e8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad3e8-106">Parameters</span></span>  

 `lpString`  
 <span data-ttu-id="ad3e8-107">진행 내보낼 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="ad3e8-108">제한이 내보낸 문자열의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad3e8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad3e8-109">Requirements</span></span>  

 <span data-ttu-id="ad3e8-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad3e8-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ad3e8-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ad3e8-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad3e8-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ad3e8-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad3e8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad3e8-114">참조</span><span class="sxs-lookup"><span data-stu-id="ad3e8-114">See also</span></span>

- [<span data-ttu-id="ad3e8-115">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ad3e8-115">ICeeGen Interface</span></span>](iceegen-interface.md)
