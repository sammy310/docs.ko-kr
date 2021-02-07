---
description: '자세히 알아보기: IMetaDataImport:: GetNameFromToken 메서드'
title: IMetaDataImport::GetNameFromToken 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNameFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNameFromToken
helpviewer_keywords:
- GetNameFromToken method [.NET Framework metadata]
- IMetaDataImport::GetNameFromToken method [.NET Framework metadata]
ms.assetid: 32114ecf-8916-4ab2-a201-179c017344f1
topic_type:
- apiref
ms.openlocfilehash: 6195020a2b291a47e908b257896bdba64b0a40d9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720854"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="6cab6-103">IMetaDataImport::GetNameFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="6cab6-103">IMetaDataImport::GetNameFromToken Method</span></span>

<span data-ttu-id="6cab6-104">지정한 메타데이터 토큰에서 참조된 개체의 UTF-8 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cab6-104">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="6cab6-105">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab6-105">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cab6-106">구문</span><span class="sxs-lookup"><span data-stu-id="6cab6-106">Syntax</span></span>  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cab6-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6cab6-107">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="6cab6-108">진행 이름을 반환할 개체를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="6cab6-108">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="6cab6-109">제한이 힙의 UTF-8 개체 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6cab6-109">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6cab6-110">설명</span><span class="sxs-lookup"><span data-stu-id="6cab6-110">Remarks</span></span>  

 <span data-ttu-id="6cab6-111">`GetNameFromToken`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab6-111">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="6cab6-112">또는 메서드를 호출 하 여 `GetFieldProps` 필드 또는 메서드에 대 한 등 필요한 특정 형식의 토큰 속성을 가져옵니다 `GetMethodProps` .</span><span class="sxs-lookup"><span data-stu-id="6cab6-112">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cab6-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6cab6-113">Requirements</span></span>  

 <span data-ttu-id="6cab6-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6cab6-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cab6-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6cab6-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6cab6-116">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cab6-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6cab6-117">**.NET Framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="6cab6-117">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cab6-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6cab6-118">See also</span></span>

- [<span data-ttu-id="6cab6-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6cab6-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6cab6-120">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6cab6-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
