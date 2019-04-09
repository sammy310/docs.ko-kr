---
title: ImportFileEx 메서드
ms.date: 03/30/2017
api_name:
- IALink2.ImportFileEx
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFileEx
helpviewer_keywords:
- ImportFileEx method
ms.assetid: ad276f3f-b303-46ac-97e0-66a377adaa4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b3cf91ad4e048ddfccb4086f36923f33d754ac0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59131042"
---
# <a name="importfileex-method"></a><span data-ttu-id="59f2a-102">ImportFileEx 메서드</span><span class="sxs-lookup"><span data-stu-id="59f2a-102">ImportFileEx Method</span></span>
<span data-ttu-id="59f2a-103">가져오기는 어셈블리 또는 바인딩되지 않은 모듈을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f2a-103">Imports indicated assembly or unbound module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59f2a-104">구문</span><span class="sxs-lookup"><span data-stu-id="59f2a-104">Syntax</span></span>  
  
```  
HRESULT ImportFileEx(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    DWORD dwOpenFlags,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="59f2a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59f2a-105">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="59f2a-106">가져올 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="59f2a-106">Fully qualified name of file from which to import.</span></span>  
  
 `pszTargetName`  
 <span data-ttu-id="59f2a-107">대상 파일의 선택적 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="59f2a-107">Optional name of target file.</span></span>  
  
 `fSmartImport`  
 <span data-ttu-id="59f2a-108">TRUE 이면 ImportTypes 되, 그렇지 않으면 가져오기는 수동으로 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f2a-108">If TRUE, ImportTypes is used, otherwise importing must be performed manually.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="59f2a-109">에 전달 하는 플래그 [OpenScope 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="59f2a-109">Flags to be passed along to [OpenScope Method](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md).</span></span>  
  
 `pImportToken`  
 <span data-ttu-id="59f2a-110">가져올 파일의 ID를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="59f2a-110">Receives ID of the file being imported.</span></span>  
  
 `ppAssemblyScope`  
 <span data-ttu-id="59f2a-111">어셈블리 가져오기 범위를 받는 [IMetaDataAssemblyImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="59f2a-111">Receives assembly import scope [IMetaDataAssemblyImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interface.</span></span> <span data-ttu-id="59f2a-112">파일 어셈블리가 아닌 경우 NULL로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59f2a-112">Is set to NULL if file is not an assembly.</span></span>  
  
 `pdwCountOfScopes`  
 <span data-ttu-id="59f2a-113">가져온된 파일 및/또는 범위에 대 한 개수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="59f2a-113">Receives count of imported files and/or scopes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59f2a-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="59f2a-114">Return Value</span></span>  
 <span data-ttu-id="59f2a-115">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59f2a-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59f2a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59f2a-116">Requirements</span></span>  
 <span data-ttu-id="59f2a-117">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="59f2a-117">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59f2a-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="59f2a-118">See also</span></span>

- [<span data-ttu-id="59f2a-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59f2a-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="59f2a-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59f2a-120">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="59f2a-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="59f2a-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
