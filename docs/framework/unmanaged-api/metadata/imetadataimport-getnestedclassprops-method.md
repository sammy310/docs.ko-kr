---
description: '자세히 알아보기: IMetaDataImport:: GetNestedClassProps 메서드'
title: IMetaDataImport::GetNestedClassProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNestedClassProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNestedClassProps
helpviewer_keywords:
- GetNestedClassProps method [.NET Framework metadata]
- IMetaDataImport::GetNestedClassProps method [.NET Framework metadata]
ms.assetid: 704d19f1-bdef-4745-af8c-6476eb246fb3
topic_type:
- apiref
ms.openlocfilehash: 5fd812bf9b7725d520b14284db400bb50e82c25b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99677539"
---
# <a name="imetadataimportgetnestedclassprops-method"></a><span data-ttu-id="e095b-103">IMetaDataImport::GetNestedClassProps 메서드</span><span class="sxs-lookup"><span data-stu-id="e095b-103">IMetaDataImport::GetNestedClassProps Method</span></span>

<span data-ttu-id="e095b-104">지정 된 중첩 형식의 부모에 대 한 TypeDef 토큰을 가져옵니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="e095b-104">Gets the TypeDef token for the parent <xref:System.Type> of the specified nested type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e095b-105">구문</span><span class="sxs-lookup"><span data-stu-id="e095b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNestedClassProps (  
   [in]   mdTypeDef      tdNestedClass,  
   [out]  mdTypeDef      *ptdEnclosingClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e095b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e095b-106">Parameters</span></span>  

 `tdNestedClass`  
 <span data-ttu-id="e095b-107">진행 부모 클래스 토큰을 반환할를 나타내는 TypeDef 토큰 <xref:System.Type> 입니다.</span><span class="sxs-lookup"><span data-stu-id="e095b-107">[in] A TypeDef token representing the <xref:System.Type> to return the parent class token for.</span></span>  
  
 `ptdEnclosingClass`  
 <span data-ttu-id="e095b-108">제한이 에 중첩 된의 TypeDef 토큰에 대 한 포인터입니다 <xref:System.Type> `tdNestedClass` .</span><span class="sxs-lookup"><span data-stu-id="e095b-108">[out] A pointer to the TypeDef token for the <xref:System.Type> that `tdNestedClass` is nested in.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e095b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e095b-109">Requirements</span></span>  

 <span data-ttu-id="e095b-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e095b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e095b-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="e095b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e095b-112">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e095b-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e095b-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e095b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e095b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e095b-114">See also</span></span>

- [<span data-ttu-id="e095b-115">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e095b-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e095b-116">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e095b-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
