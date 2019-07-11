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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d500584afd608f79e41e932be259d29ae51db2db
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781579"
---
# <a name="imetadataimport2getversionstring-method"></a><span data-ttu-id="635e7-102">IMetaDataImport2::GetVersionString 메서드</span><span class="sxs-lookup"><span data-stu-id="635e7-102">IMetaDataImport2::GetVersionString Method</span></span>
<span data-ttu-id="635e7-103">어셈블리를 빌드하는 런타임의 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="635e7-103">Gets the version number of the runtime that was used to build the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="635e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="635e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString (  
   [out] LPWSTR      pwzBuf,  
   [in]  DWORD       ccBufSize,  
   [out] DWORD       *pccBufSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="635e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="635e7-105">Parameters</span></span>  
 `pwzBuf`  
 <span data-ttu-id="635e7-106">[out] 버전을 지정 하는 문자열을 저장할 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="635e7-106">[out] An array to store the string that specifies the version.</span></span>  
  
 `ccBufSize`  
 <span data-ttu-id="635e7-107">[in] 와이드 문자에서 크기의는 `pwzBuf` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="635e7-107">[in] The size, in wide characters, of the `pwzBuf` array.</span></span>  
  
 `pccBufSize`  
 <span data-ttu-id="635e7-108">[out] 반환 되는 null 종결자를 포함 하는 와이드 문자의 수를 `pwzBuf` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="635e7-108">[out] The number of wide characters, including a null terminator, returned in the `pwzBuf` array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="635e7-109">설명</span><span class="sxs-lookup"><span data-stu-id="635e7-109">Remarks</span></span>  
 <span data-ttu-id="635e7-110">`GetVersionString` 메서드는 현재 메타 데이터 범위의 빌드 대상 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="635e7-110">The `GetVersionString` method gets the built-for version of the current metadata scope.</span></span> <span data-ttu-id="635e7-111">범위를 저장 한 적 하는 경우 빌드 대상 버전을 갖지 않습니다 및 빈 문자열이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="635e7-111">If the scope has never been saved, it will not have a built-for version, and an empty string will be returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="635e7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="635e7-112">Requirements</span></span>  
 <span data-ttu-id="635e7-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="635e7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="635e7-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="635e7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="635e7-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="635e7-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="635e7-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="635e7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="635e7-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="635e7-117">See also</span></span>

- [<span data-ttu-id="635e7-118">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="635e7-118">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="635e7-119">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="635e7-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
