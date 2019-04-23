---
title: LinkResource 메서드
ms.date: 03/30/2017
api_name:
- IALink.LinkResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- LinkResource
helpviewer_keywords:
- LinkResource method
ms.assetid: c404acb3-4c59-4100-9a4c-483cbdb1d736
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e851c1bd56c0e9ece02fb06c0dcd9975a5b02ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079438"
---
# <a name="linkresource-method"></a><span data-ttu-id="b85f1-102">LinkResource 메서드</span><span class="sxs-lookup"><span data-stu-id="b85f1-102">LinkResource Method</span></span>
<span data-ttu-id="b85f1-103">리소스의 링크를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85f1-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b85f1-104">구문</span><span class="sxs-lookup"><span data-stu-id="b85f1-104">Syntax</span></span>  
  
```  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b85f1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b85f1-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="b85f1-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b85f1-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="b85f1-107">파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b85f1-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="b85f1-108">(옵션) 새 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b85f1-108">Optional new file name.</span></span> <span data-ttu-id="b85f1-109">Null이 아닌 `pszFileName` pszNewLocation에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b85f1-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="b85f1-110">리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b85f1-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b85f1-111">내게 필요한 옵션 플래그와 같은 `mrPublic` 고 `mrPrivate`입니다.</span><span class="sxs-lookup"><span data-stu-id="b85f1-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="b85f1-112">이 매개 변수를 전달할 수 있습니다 [DefineManifestResource 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b85f1-112">This parameter may be passed to [DefineManifestResource Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b85f1-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="b85f1-113">Return Value</span></span>  
 <span data-ttu-id="b85f1-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b85f1-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b85f1-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b85f1-115">Requirements</span></span>  
 <span data-ttu-id="b85f1-116">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b85f1-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b85f1-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="b85f1-117">See also</span></span>

- [<span data-ttu-id="b85f1-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b85f1-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="b85f1-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b85f1-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="b85f1-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="b85f1-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
