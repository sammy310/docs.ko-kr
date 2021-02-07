---
description: '자세히 알아보기: IMetaDataAssemblyImport:: CloseEnum 메서드'
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
ms.openlocfilehash: 3ff234fac905a058ed832d58a0f996a2c7393ed0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678083"
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="1fba5-103">IMetaDataAssemblyImport::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="1fba5-103">IMetaDataAssemblyImport::CloseEnum Method</span></span>

<span data-ttu-id="1fba5-104">지정 된 열거형 인스턴스에 대 한 참조를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fba5-104">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fba5-105">구문</span><span class="sxs-lookup"><span data-stu-id="1fba5-105">Syntax</span></span>  
  
```cpp  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fba5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1fba5-106">Parameters</span></span>  

 `hEnum`  
 <span data-ttu-id="1fba5-107">진행 닫을 열거형 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="1fba5-107">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fba5-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1fba5-108">Requirements</span></span>  

 <span data-ttu-id="1fba5-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1fba5-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fba5-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="1fba5-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1fba5-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fba5-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1fba5-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fba5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fba5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1fba5-113">See also</span></span>

- [<span data-ttu-id="1fba5-114">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fba5-114">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
