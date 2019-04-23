---
title: ICeeGen::GetSectionCreate 메서드
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9768dfd43b6b60df1660c48cb6d6f498b049e256
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103313"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="90af8-102">ICeeGen::GetSectionCreate 메서드</span><span class="sxs-lookup"><span data-stu-id="90af8-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="90af8-103">생성 하 고 지정한 이름 및 플래그 값을 사용 하 여 코드 섹션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="90af8-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="90af8-104">이 메서드는 사용 되지 않습니다 및 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="90af8-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90af8-105">구문</span><span class="sxs-lookup"><span data-stu-id="90af8-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90af8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90af8-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="90af8-107">[in] 만들 섹션의 이름을 지정 하는 문자열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="90af8-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="90af8-108">[in] 옵션을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="90af8-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="90af8-109">[out] 새로 생성된 된 코드 섹션에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="90af8-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90af8-110">설명</span><span class="sxs-lookup"><span data-stu-id="90af8-110">Remarks</span></span>  
 <span data-ttu-id="90af8-111">호출 `GetSectionCreate` 다른 메서드에서 처리 되지 않는 특수 섹션 요구 사항이 있는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="90af8-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90af8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="90af8-112">Requirements</span></span>  
 <span data-ttu-id="90af8-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="90af8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90af8-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="90af8-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90af8-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="90af8-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90af8-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90af8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90af8-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="90af8-117">See also</span></span>

- [<span data-ttu-id="90af8-118">ICeeGen 인터페이스</span><span class="sxs-lookup"><span data-stu-id="90af8-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
