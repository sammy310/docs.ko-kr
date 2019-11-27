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
# <a name="iceegengetilsection-method"></a><span data-ttu-id="7d9b6-102">ICeeGen::GetIlSection 메서드</span><span class="sxs-lookup"><span data-stu-id="7d9b6-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="7d9b6-103">지정 된 핸들이 참조 하는 중간 언어 코드 베이스의 섹션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b6-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="7d9b6-104">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b6-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d9b6-105">구문</span><span class="sxs-lookup"><span data-stu-id="7d9b6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7d9b6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7d9b6-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="7d9b6-107">진행 가져올 섹션에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b6-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7d9b6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7d9b6-108">Requirements</span></span>  
 <span data-ttu-id="7d9b6-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d9b6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d9b6-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="7d9b6-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7d9b6-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7d9b6-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7d9b6-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d9b6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d9b6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d9b6-113">See also</span></span>

- [<span data-ttu-id="7d9b6-114">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7d9b6-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
