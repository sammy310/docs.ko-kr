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
ms.openlocfilehash: 94261b7796166cf482a7de990551890e4722dd3b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177733"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="12336-102">IMetaDataEmit::DefineModuleRef 메서드</span><span class="sxs-lookup"><span data-stu-id="12336-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="12336-103">지정된 이름을 가진 모듈의 메타데이터 서명을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12336-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12336-104">구문</span><span class="sxs-lookup"><span data-stu-id="12336-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12336-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12336-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="12336-106">【인】 다른 메타데이터 파일(일반적으로 DLL)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="12336-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="12336-107">파일 이름만 입니다.</span><span class="sxs-lookup"><span data-stu-id="12336-107">This is the file name only.</span></span> <span data-ttu-id="12336-108">전체 경로 이름을 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="12336-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="12336-109">【아웃】 할당된 `mdModuleRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="12336-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12336-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12336-110">Requirements</span></span>  
 <span data-ttu-id="12336-111">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12336-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12336-112">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="12336-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12336-113">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="12336-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="12336-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12336-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12336-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12336-115">See also</span></span>

- [<span data-ttu-id="12336-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12336-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="12336-117">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12336-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
