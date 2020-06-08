---
title: IMetaDataImport2::GetVersionString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetVersionString
helpviewer_keywords:
- GetVersionString method, IMetaDataImport2 interface [.NET Framework metadata]
- IMetaDataImport2::GetVersionString method [.NET Framework metadata]
ms.assetid: 308183ee-fd44-4432-9d86-ef00d181b49b
topic_type:
- apiref
ms.openlocfilehash: 84cf5ac9eab5749d3bdc63670fe5c31bfb62abcd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490409"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="9d41d-102">IMetaDataImport2::GetVersionString 메서드</span><span class="sxs-lookup"><span data-stu-id="9d41d-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="9d41d-103">어셈블리를 빌드하는 데 사용 된 런타임의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9d41d-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d41d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9d41d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d41d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9d41d-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="9d41d-106">제한이 버전을 지정 하는 문자열을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9d41d-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="9d41d-107">진행 배열의 크기 (와이드 문자) `pwzBuf` 입니다.</span><span class="sxs-lookup"><span data-stu-id="9d41d-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="9d41d-108">제한이 배열에 반환 된 null 종결자를 포함 하는 와이드 문자 수입니다 `pwzBuf` .</span><span class="sxs-lookup"><span data-stu-id="9d41d-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d41d-109">설명</span><span class="sxs-lookup"><span data-stu-id="9d41d-109">Remarks</span></span>  
 <span data-ttu-id="9d41d-110">`GetVersionString`메서드는 현재 메타 데이터 범위의 기본 제공 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9d41d-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="9d41d-111">범위를 저장 하지 않은 경우에는 기본 제공 버전이 없으며 빈 문자열이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d41d-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d41d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d41d-112">Requirements</span></span>  
 <span data-ttu-id="9d41d-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9d41d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d41d-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="9d41d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d41d-115">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9d41d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d41d-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d41d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d41d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d41d-117">See also</span></span>

- [<span data-ttu-id="9d41d-118">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d41d-118">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="9d41d-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9d41d-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
