---
title: IMetaDataAssemblyImport::CloseEnum 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::CloseEnum
helpviewer_keywords:
- CloseEnum method, IMetaDataAssemblyImport interface [.NET Framework metadata]
- IMetaDataAssemblyImport::CloseEnum method [.NET Framework metadata]
ms.assetid: c9df4087-12b3-46d9-b075-9067dd7805df
topic_type:
- apiref
ms.openlocfilehash: c037b9dce4b7530c952c75122f86335da82e1b27
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446037"
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="3a096-102">IMetaDataAssemblyImport::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="3a096-102">IMetaDataAssemblyImport::CloseEnum Method</span></span>
<span data-ttu-id="3a096-103">Releases a reference to the specified enumeration instance.</span><span class="sxs-lookup"><span data-stu-id="3a096-103">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a096-104">구문</span><span class="sxs-lookup"><span data-stu-id="3a096-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a096-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a096-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="3a096-106">[in] The enumeration instance to be closed.</span><span class="sxs-lookup"><span data-stu-id="3a096-106">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a096-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a096-107">Requirements</span></span>  
 <span data-ttu-id="3a096-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a096-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a096-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3a096-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a096-110">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a096-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a096-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a096-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a096-112">참조</span><span class="sxs-lookup"><span data-stu-id="3a096-112">See also</span></span>

- [<span data-ttu-id="3a096-113">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a096-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
