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
ms.openlocfilehash: d2ce26daa5f5c36e4073eee653cc650c1a8d54c9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708945"
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="6d1e9-102">IMetaDataAssemblyImport::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="6d1e9-102">IMetaDataAssemblyImport::CloseEnum Method</span></span>

<span data-ttu-id="6d1e9-103">지정 된 열거형 인스턴스에 대 한 참조를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d1e9-103">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d1e9-104">구문</span><span class="sxs-lookup"><span data-stu-id="6d1e9-104">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d1e9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6d1e9-105">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="6d1e9-106">진행 닫을 열거형 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="6d1e9-106">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d1e9-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6d1e9-107">Requirements</span></span>  

 <span data-ttu-id="6d1e9-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6d1e9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d1e9-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6d1e9-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6d1e9-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d1e9-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6d1e9-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d1e9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d1e9-112">참조</span><span class="sxs-lookup"><span data-stu-id="6d1e9-112">See also</span></span>

- [<span data-ttu-id="6d1e9-113">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6d1e9-113">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
