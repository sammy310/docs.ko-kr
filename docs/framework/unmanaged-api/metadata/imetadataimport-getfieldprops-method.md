---
title: IMetaDataImport::GetFieldProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldProps
helpviewer_keywords:
- IMetaDataImport::GetFieldProps method [.NET Framework metadata]
- GetFieldProps method [.NET Framework metadata]
ms.assetid: 7b0e9b10-8cef-4ba6-8432-40bf63e65ab1
topic_type:
- apiref
ms.openlocfilehash: 458a90bc47711d9f831805faa8468a49f3e0d305
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704002"
---
# <a name="imetadataimportgetfieldprops-method"></a><span data-ttu-id="301cf-102">IMetaDataImport::GetFieldProps 메서드</span><span class="sxs-lookup"><span data-stu-id="301cf-102">IMetaDataImport::GetFieldProps Method</span></span>

<span data-ttu-id="301cf-103">지정한 FieldDef 토큰이 참조하는 필드와 연결된 메타데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-103">Gets metadata associated with the field referenced by the specified FieldDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="301cf-104">구문</span><span class="sxs-lookup"><span data-stu-id="301cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldProps (  
   [in]  mdFieldDef        mb,
   [out] mdTypeDef         *pClass,  
   [out] LPWSTR            szField,  
   [in]  ULONG             cchField,
   [out] ULONG             *pchField,  
   [out] DWORD             *pdwAttr,  
   [in]  PCCOR_SIGNATURE   *ppvSigBlob,
   [out] ULONG             *pcbSigBlob,
   [out] DWORD             *pdwCPlusTypeFlag,
   [out] UVCP_CONSTANT     *ppValue,  
   [out] ULONG             *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="301cf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="301cf-105">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="301cf-106">진행 연결 된 메타 데이터를 가져올 필드를 나타내는 FieldDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-106">[in] A FieldDef token that represents the field to get associated metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="301cf-107">제한이 필드가 속한 클래스의 형식을 나타내는 TypeDef 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-107">[out] A pointer to a TypeDef token that represents the type of the class that the field belongs to.</span></span>  
  
 `szField`  
 <span data-ttu-id="301cf-108">제한이 필드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-108">[out] The name of the field.</span></span>  
  
 `cchField`  
 <span data-ttu-id="301cf-109">진행 *Szfield* 에 대 한 버퍼의 와이드 문자 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-109">[in] The size in wide characters of the buffer for *szField*.</span></span>  
  
 `pchField`  
 <span data-ttu-id="301cf-110">제한이 반환 된 버퍼의 실제 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-110">[out] The actual size of the returned buffer.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="301cf-111">제한이 필드의 메타 데이터와 연결 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-111">[out] Flags associated with the field's metadata.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="301cf-112">진행 필드를 설명 하는 이진 메타 데이터 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-112">[in] A pointer to the binary metadata value that describes the field.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="301cf-113">제한이 의 크기 (바이트) `ppvSigBlob` 입니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-113">[out] The size in bytes of `ppvSigBlob`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="301cf-114">제한이 필드의 값 형식을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-114">[out] A flag that specifies the value type of the field.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="301cf-115">제한이 필드에 대 한 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-115">[out] A constant value for the field.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="301cf-116">제한이 의 문자 크기 `ppValue` 이거나, 문자열이 없는 경우 0입니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-116">[out] The size in chars of `ppValue`, or zero if no string exists.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="301cf-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="301cf-117">Requirements</span></span>  

 <span data-ttu-id="301cf-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="301cf-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="301cf-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="301cf-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="301cf-120">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="301cf-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="301cf-121">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="301cf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="301cf-122">참조</span><span class="sxs-lookup"><span data-stu-id="301cf-122">See also</span></span>

- [<span data-ttu-id="301cf-123">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="301cf-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="301cf-124">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="301cf-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
