---
title: Cert2spc.exe(SPC 테스트 도구)
description: Cert2spc.exe 즉, SPC 테스트 도구를 사용합니다. 이 도구는 하나 이상의 X.509 인증서에서 SPC(소프트웨어 게시자 인증서)를 만듭니다.
ms.date: 03/30/2017
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
ms.openlocfilehash: 96b4c05f6c9af6fc78aa55b248a88de84e2d4ac8
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258284"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a><span data-ttu-id="46af1-104">Cert2spc.exe(SPC 테스트 도구)</span><span class="sxs-lookup"><span data-stu-id="46af1-104">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>

<span data-ttu-id="46af1-105">SPC(소프트웨어 게시자 인증서) 테스트 도구를 사용하면 하나 이상의 X.509 인증서에서 SPC를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-105">The Software Publisher Certificate Test tool creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="46af1-106">Cert2spc.exe는 테스트 전용이며,</span><span class="sxs-lookup"><span data-stu-id="46af1-106">Cert2spc.exe is for test purposes only.</span></span> <span data-ttu-id="46af1-107">VeriSign 또는 Thawte 같은 인증 기관에서 유효한 SPC를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-107">You can obtain a valid SPC from a Certification Authority such as VeriSign or Thawte.</span></span> <span data-ttu-id="46af1-108">X.509 인증서를 만드는 방법은 [Makecert.exe(인증서 작성 도구)](/windows/desktop/SecCrypto/makecert)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46af1-108">For more information about creating X.509 certificates, see [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert).</span></span>  
  
 <span data-ttu-id="46af1-109">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-109">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="46af1-110">도구를 실행하려면 [개발자용 명령줄 셸](/visualstudio/ide/reference/command-prompt-powershell)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-110">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span>  
  
 <span data-ttu-id="46af1-111">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-111">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46af1-112">구문</span><span class="sxs-lookup"><span data-stu-id="46af1-112">Syntax</span></span>  
  
```console  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
## <a name="parameters"></a><span data-ttu-id="46af1-113">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46af1-113">Parameters</span></span>  
  
|<span data-ttu-id="46af1-114">인수</span><span class="sxs-lookup"><span data-stu-id="46af1-114">Argument</span></span>|<span data-ttu-id="46af1-115">Description</span><span class="sxs-lookup"><span data-stu-id="46af1-115">Description</span></span>|  
|--------------|-----------------|  
|`certN.cer`|<span data-ttu-id="46af1-116">SPC 파일에 포함할 X.509 인증서의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-116">The name of an X.509 certificate to include in the SPC file.</span></span> <span data-ttu-id="46af1-117">여러 개의 이름을 공백으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-117">You can specify multiple names separated by spaces.</span></span>|  
|`crlN.crl`|<span data-ttu-id="46af1-118">SPC 파일에 포함할 인증서 해지 목록의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-118">The name of a certificate revocation list to include in the SPC file.</span></span> <span data-ttu-id="46af1-119">여러 개의 이름을 공백으로 구분하여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-119">You can specify multiple names separated by spaces.</span></span>|  
|`outputSPCfile.spc`|<span data-ttu-id="46af1-120">X.509 인증서가 들어 있는 PKCS #7 개체의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-120">The name of the PKCS #7 object that will contain the X.509 certificates.</span></span>|  
  
|<span data-ttu-id="46af1-121">옵션</span><span class="sxs-lookup"><span data-stu-id="46af1-121">Option</span></span>|<span data-ttu-id="46af1-122">Description</span><span class="sxs-lookup"><span data-stu-id="46af1-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="46af1-123">**/?**</span><span class="sxs-lookup"><span data-stu-id="46af1-123">**/?**</span></span>|<span data-ttu-id="46af1-124">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-124">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="46af1-125">예</span><span class="sxs-lookup"><span data-stu-id="46af1-125">Examples</span></span>  

 <span data-ttu-id="46af1-126">다음 명령을 사용하여 `myCertificate.cer`에서 SPC를 만들고 이를 `mySPCFile.spc`에 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-126">The following command creates an SPC from `myCertificate.cer` and places it in `mySPCFile.spc`.</span></span>  
  
```console
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 <span data-ttu-id="46af1-127">다음 명령을 사용하여 `oneCertificate.cer` 및 `twoCertificate.cer`에서 SPC를 만들고 이를 `mySPCFile.spc`에 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="46af1-127">The following command creates an SPC from `oneCertificate.cer` and `twoCertificate.cer`, and places it in `mySPCFile.spc`.</span></span>  
  
```console
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a><span data-ttu-id="46af1-128">참조</span><span class="sxs-lookup"><span data-stu-id="46af1-128">See also</span></span>

- [<span data-ttu-id="46af1-129">도구</span><span class="sxs-lookup"><span data-stu-id="46af1-129">Tools</span></span>](index.md)
- [<span data-ttu-id="46af1-130">Makecert.exe(인증서 작성 도구)</span><span class="sxs-lookup"><span data-stu-id="46af1-130">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)
- [<span data-ttu-id="46af1-131">개발자 명령줄 셸</span><span class="sxs-lookup"><span data-stu-id="46af1-131">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
