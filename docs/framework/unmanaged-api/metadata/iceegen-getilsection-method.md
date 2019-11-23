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
ms.openlocfilehash: 7ef944fd06d07dc8c4e49061a5e72d8acc4d0465
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436342"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="b7c20-102">ICeeGen::GetIlSection 메서드</span><span class="sxs-lookup"><span data-stu-id="b7c20-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="b7c20-103">Gets the section of the intermediate language code base referenced by the specified handle.</span><span class="sxs-lookup"><span data-stu-id="b7c20-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="b7c20-104">This method is obsolete and should not be used.</span><span class="sxs-lookup"><span data-stu-id="b7c20-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7c20-105">구문</span><span class="sxs-lookup"><span data-stu-id="b7c20-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7c20-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7c20-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="b7c20-107">[in] The handle to the section to get.</span><span class="sxs-lookup"><span data-stu-id="b7c20-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7c20-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b7c20-108">Requirements</span></span>  
 <span data-ttu-id="b7c20-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7c20-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7c20-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b7c20-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7c20-111">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b7c20-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7c20-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7c20-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c20-113">참조</span><span class="sxs-lookup"><span data-stu-id="b7c20-113">See also</span></span>

- [<span data-ttu-id="b7c20-114">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b7c20-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
