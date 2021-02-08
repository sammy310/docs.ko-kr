---
description: '자세히 알아보기: IMetaDataImport:: GetTypeRefProps 메서드'
title: IMetaDataImport::GetTypeRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeRefProps
helpviewer_keywords:
- IMetaDataImport::GetTypeRefProps method [.NET Framework metadata]
- GetTypeRefProps method [.NET Framework metadata]
ms.assetid: 01837955-ce1e-4068-b338-fd473bd77d1d
topic_type:
- apiref
ms.openlocfilehash: 8d4741ca2d04aaa4af48fee2cf6485de3403a525
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789127"
---
# <a name="imetadataimportgettyperefprops-method"></a><span data-ttu-id="82826-103">IMetaDataImport::GetTypeRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="82826-103">IMetaDataImport::GetTypeRefProps Method</span></span>

<span data-ttu-id="82826-104">지정 된 TypeRef 토큰이 참조 하는와 연결 된 메타 데이터를 가져옵니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="82826-104">Gets the metadata associated with the <xref:System.Type> referenced by the specified TypeRef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82826-105">구문</span><span class="sxs-lookup"><span data-stu-id="82826-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeRefProps (  
   [in]  mdTypeRef   tr,  
   [out] mdToken     *ptkResolutionScope,  
   [out] LPWSTR      szName,  
   [in]  ULONG       cchName,  
   [out] ULONG       *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82826-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82826-106">Parameters</span></span>  

 `tr`  
 <span data-ttu-id="82826-107">진행 메타 데이터를 반환할 형식을 나타내는 TypeRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="82826-107">[in] The TypeRef token that represents the type to return metadata for.</span></span>  
  
 `ptkResolutionScope`  
 <span data-ttu-id="82826-108">제한이 참조가 생성 되는 범위에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="82826-108">[out] A pointer to the scope in which the reference is made.</span></span> <span data-ttu-id="82826-109">이 값은 AssemblyRef 또는 ModuleRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="82826-109">This value is an AssemblyRef or ModuleRef token.</span></span>  
  
 `szName`  
 <span data-ttu-id="82826-110">제한이 형식 이름을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="82826-110">[out] A buffer containing the type name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="82826-111">진행 에서 요청 된 크기 (와이드 문자) `szName` 입니다.</span><span class="sxs-lookup"><span data-stu-id="82826-111">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="82826-112">제한이 의 와이드 문자에서 반환 되는 크기입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="82826-112">[out] The returned size in wide characters of `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82826-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82826-113">Requirements</span></span>  

 <span data-ttu-id="82826-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82826-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82826-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="82826-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82826-116">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82826-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82826-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82826-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82826-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82826-118">See also</span></span>

- [<span data-ttu-id="82826-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82826-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="82826-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82826-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
