---
title: ICeeGen::GetString 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
ms.openlocfilehash: ada126b41f1c634f7d8daa58480406ac26f92377
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177899"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="3fe2a-102">ICeeGen::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="3fe2a-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="3fe2a-103">지정된 상대 가상 주소에 저장된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="3fe2a-104">이 메서드는 더 이상 사용되지 않으며 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fe2a-105">구문</span><span class="sxs-lookup"><span data-stu-id="3fe2a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fe2a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3fe2a-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="3fe2a-107">【인】 반환할 문자열의 상대적인 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="3fe2a-108">【아웃】 반환된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fe2a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3fe2a-109">Requirements</span></span>  
 <span data-ttu-id="3fe2a-110">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fe2a-111">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="3fe2a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3fe2a-112">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="3fe2a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3fe2a-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fe2a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fe2a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fe2a-114">See also</span></span>

- [<span data-ttu-id="3fe2a-115">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3fe2a-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
