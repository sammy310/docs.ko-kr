---
title: IMetaDataAssemblyImport::GetAssemblyFromScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type:
- apiref
ms.openlocfilehash: 953aa16566c2a15939fbd556f478bbdb3c0c77d0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448246"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="5d0a2-102">IMetaDataAssemblyImport::GetAssemblyFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="5d0a2-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="5d0a2-103">Gets a pointer to the assembly in the current scope.</span><span class="sxs-lookup"><span data-stu-id="5d0a2-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d0a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d0a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d0a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d0a2-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="5d0a2-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span><span class="sxs-lookup"><span data-stu-id="5d0a2-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d0a2-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d0a2-107">Requirements</span></span>  
 <span data-ttu-id="5d0a2-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5d0a2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d0a2-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5d0a2-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d0a2-110">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d0a2-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d0a2-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d0a2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d0a2-112">참조</span><span class="sxs-lookup"><span data-stu-id="5d0a2-112">See also</span></span>

- [<span data-ttu-id="5d0a2-113">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d0a2-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
