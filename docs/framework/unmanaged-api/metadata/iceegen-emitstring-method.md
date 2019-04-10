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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59209959"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="a5228-102">ICeeGen::EmitString 메서드</span><span class="sxs-lookup"><span data-stu-id="a5228-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="a5228-103">코드 베이스에 지정된 된 문자열을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a5228-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="a5228-104">이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5228-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5228-105">구문</span><span class="sxs-lookup"><span data-stu-id="a5228-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5228-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a5228-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="a5228-107">[in] 내보낼 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a5228-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="a5228-108">[out] 내보낸된 문자열의 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a5228-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5228-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5228-109">Requirements</span></span>  
 <span data-ttu-id="a5228-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a5228-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5228-111">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a5228-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5228-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="a5228-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="a5228-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="a5228-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a5228-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="a5228-114">See also</span></span>

- [<span data-ttu-id="a5228-115">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5228-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
