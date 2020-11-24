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
ms.openlocfilehash: 4f2f13976dfd4e5601bf8b54bed7b851884fbb9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690449"
---
# <a name="linkresource-method"></a><span data-ttu-id="11d2e-102">LinkResource 메서드</span><span class="sxs-lookup"><span data-stu-id="11d2e-102">LinkResource Method</span></span>

<span data-ttu-id="11d2e-103">리소스의 링크입니다.</span><span class="sxs-lookup"><span data-stu-id="11d2e-103">Links in a resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11d2e-104">구문</span><span class="sxs-lookup"><span data-stu-id="11d2e-104">Syntax</span></span>  
  
```cpp  
HRESULT LinkResource(  
    mdAssembly  AssemblyID,  
    LPCWSTR     pszFileName,  
    LPCWSTR     pszNewLocation,  
    LPCWSTR     pszResourceName,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="11d2e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11d2e-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="11d2e-106">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="11d2e-106">ID of the assembly.</span></span>  
  
 `pszFileName`  
 <span data-ttu-id="11d2e-107">파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="11d2e-107">Name of the file.</span></span>  
  
 `pszNewLocation`  
 <span data-ttu-id="11d2e-108">선택적 새 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="11d2e-108">Optional new file name.</span></span> <span data-ttu-id="11d2e-109">NULL이 아닌 경우 `pszFileName` pszNewLocation에 복사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11d2e-109">If non-NULL, `pszFileName` will be copied to pszNewLocation.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="11d2e-110">리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="11d2e-110">Name of the resource.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="11d2e-111">및와 같은 내게 필요한 옵션 플래그 `mrPublic` `mrPrivate` 입니다.</span><span class="sxs-lookup"><span data-stu-id="11d2e-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="11d2e-112">이 매개 변수는 [DefineManifestResource 메서드에](../metadata/imetadataassemblyemit-definemanifestresource-method.md)전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11d2e-112">This parameter may be passed to [DefineManifestResource Method](../metadata/imetadataassemblyemit-definemanifestresource-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11d2e-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="11d2e-113">Return Value</span></span>  

 <span data-ttu-id="11d2e-114">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="11d2e-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11d2e-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11d2e-115">Requirements</span></span>  

 <span data-ttu-id="11d2e-116">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="11d2e-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d2e-117">참조</span><span class="sxs-lookup"><span data-stu-id="11d2e-117">See also</span></span>

- [<span data-ttu-id="11d2e-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11d2e-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="11d2e-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11d2e-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="11d2e-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="11d2e-120">ALink API</span></span>](index.md)
