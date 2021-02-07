---
description: '자세한 정보: ICeeGen:: GetIlSection 메서드'
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
ms.openlocfilehash: 44195ec55480279494620aed6db566f1c2308a6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707009"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="eed6a-103">ICeeGen::GetIlSection 메서드</span><span class="sxs-lookup"><span data-stu-id="eed6a-103">ICeeGen::GetIlSection Method</span></span>

<span data-ttu-id="eed6a-104">지정 된 핸들이 참조 하는 중간 언어 코드 베이스의 섹션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eed6a-104">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="eed6a-105">이 메서드는 사용 되지 않으므로 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eed6a-105">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eed6a-106">구문</span><span class="sxs-lookup"><span data-stu-id="eed6a-106">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eed6a-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eed6a-107">Parameters</span></span>  

 `section`  
 <span data-ttu-id="eed6a-108">진행 가져올 섹션에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="eed6a-108">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eed6a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eed6a-109">Requirements</span></span>  

 <span data-ttu-id="eed6a-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eed6a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eed6a-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="eed6a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eed6a-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eed6a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eed6a-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eed6a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eed6a-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eed6a-114">See also</span></span>

- [<span data-ttu-id="eed6a-115">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eed6a-115">ICeeGen Interface</span></span>](iceegen-interface.md)
