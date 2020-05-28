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
ms.openlocfilehash: efff491d92ac7910f43f76965ef98d1d0e4ba0aa
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004441"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="ae394-102">IMetaDataEmit::DefineModuleRef 메서드</span><span class="sxs-lookup"><span data-stu-id="ae394-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="ae394-103">지정 된 이름을 사용 하 여 모듈에 대 한 메타 데이터 서명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae394-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae394-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae394-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae394-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae394-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="ae394-106">진행 다른 메타 데이터 파일의 이름입니다 (일반적으로 DLL).</span><span class="sxs-lookup"><span data-stu-id="ae394-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="ae394-107">이는 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ae394-107">This is the file name only.</span></span> <span data-ttu-id="ae394-108">전체 경로 이름을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ae394-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="ae394-109">제한이 할당 된 `mdModuleRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ae394-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae394-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae394-110">Requirements</span></span>  
 <span data-ttu-id="ae394-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae394-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae394-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ae394-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae394-113">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae394-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae394-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae394-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae394-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae394-115">See also</span></span>

- [<span data-ttu-id="ae394-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae394-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ae394-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae394-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
