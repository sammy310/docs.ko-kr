---
title: ICeeGen::GetIlSection 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1cff5b7fadf4345b7a1d09911dc7061adc925e7a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139154"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="e251d-102">ICeeGen::GetIlSection 메서드</span><span class="sxs-lookup"><span data-stu-id="e251d-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="e251d-103">지정된 된 핸들에서 참조 기본 중간 언어 코드의 섹션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e251d-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="e251d-104">이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e251d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e251d-105">구문</span><span class="sxs-lookup"><span data-stu-id="e251d-105">Syntax</span></span>  
  
```  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e251d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e251d-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="e251d-107">[in] 가져오려는 섹션에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="e251d-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e251d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e251d-108">Requirements</span></span>  
 <span data-ttu-id="e251d-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e251d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e251d-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e251d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e251d-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="e251d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e251d-112">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="e251d-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e251d-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="e251d-113">See also</span></span>

- [<span data-ttu-id="e251d-114">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e251d-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
