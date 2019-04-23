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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1eabf5631fcfe7a187d0e203d64c7a7f4f5a819a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59209959"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="3255f-102">ICeeGen::EmitString 메서드</span><span class="sxs-lookup"><span data-stu-id="3255f-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="3255f-103">코드 베이스에 지정된 된 문자열을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="3255f-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="3255f-104">이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3255f-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3255f-105">구문</span><span class="sxs-lookup"><span data-stu-id="3255f-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3255f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3255f-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="3255f-107">[in] 내보낼 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3255f-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="3255f-108">[out] 내보낸된 문자열의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3255f-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3255f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3255f-109">Requirements</span></span>  
 <span data-ttu-id="3255f-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3255f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3255f-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3255f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3255f-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="3255f-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3255f-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3255f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3255f-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="3255f-114">See also</span></span>

- [<span data-ttu-id="3255f-115">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3255f-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
