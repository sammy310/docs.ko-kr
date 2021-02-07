---
description: '자세히 알아보기: IMetaDataImport:: GetModuleRefProps 메서드'
title: IMetaDataImport::GetModuleRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type:
- apiref
ms.openlocfilehash: 3e6b212ddad5eefb06942c3fd4b89411b277f761
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753356"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="7bdca-103">IMetaDataImport::GetModuleRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="7bdca-103">IMetaDataImport::GetModuleRefProps Method</span></span>

<span data-ttu-id="7bdca-104">지정한 메타데이터 토큰에서 참조된 모듈의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7bdca-104">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bdca-105">구문</span><span class="sxs-lookup"><span data-stu-id="7bdca-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,
   [in]  ULONG               cchName,
   [out] ULONG               *pchName
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bdca-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7bdca-106">Parameters</span></span>  

 `mur`  
 <span data-ttu-id="7bdca-107">진행 메타 데이터 정보를 가져올 모듈을 참조 하는 ModuleRef metadata 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdca-107">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="7bdca-108">제한이 모듈 이름을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdca-108">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="7bdca-109">진행 요청 된 크기 `szName` (와이드 문자)입니다.</span><span class="sxs-lookup"><span data-stu-id="7bdca-109">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="7bdca-110">제한이 와이드 문자 단위의 반환 된 크기입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="7bdca-110">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bdca-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7bdca-111">Requirements</span></span>  

 <span data-ttu-id="7bdca-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bdca-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bdca-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="7bdca-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7bdca-114">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bdca-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7bdca-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bdca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bdca-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bdca-116">See also</span></span>

- [<span data-ttu-id="7bdca-117">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7bdca-117">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="7bdca-118">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7bdca-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
