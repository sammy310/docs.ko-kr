---
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
ms.openlocfilehash: 867fb0ee4bc1a093eb7fd46e25497d585c4d9b6b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727499"
---
# <a name="imetadataimportgetnamefromtoken-method"></a><span data-ttu-id="3985c-102">IMetaDataImport::GetNameFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="3985c-102">IMetaDataImport::GetNameFromToken Method</span></span>

<span data-ttu-id="3985c-103">지정한 메타데이터 토큰에서 참조된 개체의 UTF-8 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3985c-103">Gets the UTF-8 name of the object referenced by the specified metadata token.</span></span> <span data-ttu-id="3985c-104">이 메서드는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3985c-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3985c-105">구문</span><span class="sxs-lookup"><span data-stu-id="3985c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNameFromToken (  
   [in] mdToken      tk,  
   [out] MDUTF8CSTR  *pszUtf8NamePtr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3985c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3985c-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="3985c-107">진행 이름을 반환할 개체를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3985c-107">[in] The token representing the object to return the name for.</span></span>  
  
 `pszUtf8NamePtr`  
 <span data-ttu-id="3985c-108">제한이 힙의 UTF-8 개체 이름에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3985c-108">[out] A pointer to the UTF-8 object name in the heap.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3985c-109">설명</span><span class="sxs-lookup"><span data-stu-id="3985c-109">Remarks</span></span>  

 <span data-ttu-id="3985c-110">`GetNameFromToken`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3985c-110">`GetNameFromToken` is obsolete.</span></span> <span data-ttu-id="3985c-111">또는 메서드를 호출 하 여 `GetFieldProps` 필드 또는 메서드에 대 한 등 필요한 특정 형식의 토큰 속성을 가져옵니다 `GetMethodProps` .</span><span class="sxs-lookup"><span data-stu-id="3985c-111">As an alternative, call a method to get the properties of the particular type of token required, such as `GetFieldProps` for a field or `GetMethodProps` for a method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3985c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3985c-112">Requirements</span></span>  

 <span data-ttu-id="3985c-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3985c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3985c-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3985c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3985c-115">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3985c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3985c-116">**.NET Framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="3985c-116">**.NET Framework Versions:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3985c-117">참조</span><span class="sxs-lookup"><span data-stu-id="3985c-117">See also</span></span>

- [<span data-ttu-id="3985c-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3985c-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3985c-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3985c-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
