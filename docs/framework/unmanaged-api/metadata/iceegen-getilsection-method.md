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
ms.openlocfilehash: 8bddb782e13b4e7400c7e4a8128dc333efc8141d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67746186"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="b47ab-102">ICeeGen::GetIlSection 메서드</span><span class="sxs-lookup"><span data-stu-id="b47ab-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="b47ab-103">지정된 된 핸들에서 참조 기본 중간 언어 코드의 섹션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b47ab-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="b47ab-104">이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b47ab-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b47ab-105">구문</span><span class="sxs-lookup"><span data-stu-id="b47ab-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b47ab-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b47ab-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="b47ab-107">[in] 가져오려는 섹션에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="b47ab-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b47ab-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b47ab-108">Requirements</span></span>  
 <span data-ttu-id="b47ab-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b47ab-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b47ab-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b47ab-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b47ab-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b47ab-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b47ab-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b47ab-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b47ab-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="b47ab-113">See also</span></span>

- [<span data-ttu-id="b47ab-114">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b47ab-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
