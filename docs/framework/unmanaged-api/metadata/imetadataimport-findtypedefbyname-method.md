---
title: IMetaDataImport::FindTypeDefByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindTypeDefByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindTypeDefByName
helpviewer_keywords:
- FindTypeDefByName method [.NET Framework metadata]
- IMetaDataImport::FindTypeDefByName method [.NET Framework metadata]
ms.assetid: f4c2cd88-ac28-4bad-9ab1-2cf9d2de41e6
topic_type:
- apiref
ms.openlocfilehash: df1516a916b2b48080e4f94937fba063926330ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711301"
---
# <a name="imetadataimportfindtypedefbyname-method"></a><span data-ttu-id="4eac9-102">IMetaDataImport::FindTypeDefByName 메서드</span><span class="sxs-lookup"><span data-stu-id="4eac9-102">IMetaDataImport::FindTypeDefByName Method</span></span>

<span data-ttu-id="4eac9-103">지정 된 이름을 가진의 TypeDef 메타 데이터 토큰에 대 한 포인터를 가져옵니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="4eac9-103">Gets a pointer to the TypeDef metadata token for the <xref:System.Type> with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eac9-104">구문</span><span class="sxs-lookup"><span data-stu-id="4eac9-104">Syntax</span></span>  
  
```cpp  
HRESULT FindTypeDefByName  
   [in]  LPCWSTR       szTypeDef,  
   [in]  mdToken       tkEnclosingClass,  
   [out] mdTypeDef     *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4eac9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4eac9-105">Parameters</span></span>  

 `szTypeDef`  
 <span data-ttu-id="4eac9-106">진행 TypeDef 토큰을 가져올 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4eac9-106">[in] The name of the type for which to get the TypeDef token.</span></span>  
  
 `tkEnclosingClass`  
 <span data-ttu-id="4eac9-107">진행 바깥쪽 클래스를 나타내는 TypeDef 또는 TypeRef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="4eac9-107">[in] A TypeDef or TypeRef token representing the enclosing class.</span></span> <span data-ttu-id="4eac9-108">찾을 형식이 중첩 된 클래스가 아닌 경우이 값을 NULL로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eac9-108">If the type to find is not a nested class, set this value to NULL.</span></span>  
  
 `ptd`  
 <span data-ttu-id="4eac9-109">제한이 일치 하는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4eac9-109">[out] A pointer to the matching TypeDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4eac9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4eac9-110">Requirements</span></span>  

 <span data-ttu-id="4eac9-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4eac9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eac9-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4eac9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4eac9-113">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eac9-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4eac9-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eac9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eac9-115">참조</span><span class="sxs-lookup"><span data-stu-id="4eac9-115">See also</span></span>

- [<span data-ttu-id="4eac9-116">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4eac9-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4eac9-117">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4eac9-117">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
