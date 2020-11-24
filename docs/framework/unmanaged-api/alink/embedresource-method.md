---
title: EmbedResource 메서드
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
ms.openlocfilehash: 34439b7c01dee7d7789d989b58e8944c6282b71b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676389"
---
# <a name="embedresource-method"></a><span data-ttu-id="d1dd8-102">EmbedResource 메서드</span><span class="sxs-lookup"><span data-stu-id="d1dd8-102">EmbedResource Method</span></span>

<span data-ttu-id="d1dd8-103">포함 리소스를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-103">Declares an embedded resource.</span></span> <span data-ttu-id="d1dd8-104">이 메서드는 실제로 리소스를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1dd8-105">구문</span><span class="sxs-lookup"><span data-stu-id="d1dd8-105">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1dd8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d1dd8-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="d1dd8-107">어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="d1dd8-108">리소스를 포함 하는 파일의 파일 토큰 또는 어셈블리 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="d1dd8-109">리소스의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="d1dd8-110">RVA에서 리소스의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d1dd8-111">및와 같은 내게 필요한 옵션 플래그 `mrPublic` `mrPrivate` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="d1dd8-112">이러한 플래그는 [DefineExportedType 메서드에](../metadata/imetadataassemblyemit-defineexportedtype-method.md)전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-112">These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1dd8-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="d1dd8-113">Return Value</span></span>  

 <span data-ttu-id="d1dd8-114">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1dd8-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d1dd8-115">Requirements</span></span>  

 <span data-ttu-id="d1dd8-116">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1dd8-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1dd8-117">참조</span><span class="sxs-lookup"><span data-stu-id="d1dd8-117">See also</span></span>

- [<span data-ttu-id="d1dd8-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1dd8-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="d1dd8-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1dd8-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="d1dd8-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="d1dd8-120">ALink API</span></span>](index.md)
