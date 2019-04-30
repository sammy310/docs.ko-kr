---
title: IMetaDataEmit::DefineModuleRef 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineModuleRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f52f102102cb654035d49eea0f4b0a9061475a3a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050131"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="52907-102">IMetaDataEmit::DefineModuleRef 메서드</span><span class="sxs-lookup"><span data-stu-id="52907-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="52907-103">지정 된 이름의 모듈에 대 한 메타 데이터 서명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="52907-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52907-104">구문</span><span class="sxs-lookup"><span data-stu-id="52907-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52907-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="52907-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="52907-106">[in] 다른 메타 데이터 파일을 일반적으로 DLL의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="52907-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="52907-107">이것이 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="52907-107">This is the file name only.</span></span> <span data-ttu-id="52907-108">전체 경로 이름을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="52907-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="52907-109">[out] 할당 된 `mdModuleRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="52907-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52907-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="52907-110">Requirements</span></span>  
 <span data-ttu-id="52907-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="52907-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52907-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="52907-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="52907-113">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="52907-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52907-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52907-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52907-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="52907-115">See also</span></span>

- [<span data-ttu-id="52907-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52907-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="52907-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="52907-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
