---
description: '자세히 알아보기: IMetaDataAssemblyImport:: GetAssemblyFromScope 메서드'
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
ms.openlocfilehash: 78e2862fca80dc06c37436f3d81db4b19c4ec332
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784160"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="427d9-103">IMetaDataAssemblyImport::GetAssemblyFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="427d9-103">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>

<span data-ttu-id="427d9-104">현재 범위에 있는 어셈블리에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="427d9-104">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="427d9-105">구문</span><span class="sxs-lookup"><span data-stu-id="427d9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="427d9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="427d9-106">Parameters</span></span>  

 `ptkAssembly`  
 <span data-ttu-id="427d9-107">제한이 어셈블리를 식별 하는 검색 된 토큰에 대 한 포인터입니다 `mdAssembly` .</span><span class="sxs-lookup"><span data-stu-id="427d9-107">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="427d9-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="427d9-108">Requirements</span></span>  

 <span data-ttu-id="427d9-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="427d9-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="427d9-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="427d9-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="427d9-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="427d9-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="427d9-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="427d9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="427d9-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="427d9-113">See also</span></span>

- [<span data-ttu-id="427d9-114">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="427d9-114">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
