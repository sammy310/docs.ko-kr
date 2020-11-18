---
title: '방법: 하드웨어 암호화 디바이스에 액세스'
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encryption
- key card
- cryptography
- hardware encryption
- CspParameters
ms.assetid: b0e734df-6eb4-4b16-b48c-6f0fe82d5f17
ms.openlocfilehash: c4f0b77985dea1818729af41b69a4a7d30427415
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829897"
---
# <a name="how-to-access-hardware-encryption-devices"></a><span data-ttu-id="ecb6c-102">방법: 하드웨어 암호화 디바이스에 액세스</span><span class="sxs-lookup"><span data-stu-id="ecb6c-102">How to: Access Hardware Encryption Devices</span></span>

> [!NOTE]
> <span data-ttu-id="ecb6c-103">이 문서는 Windows에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-103">This article applies to Windows.</span></span>

<span data-ttu-id="ecb6c-104"><xref:System.Security.Cryptography.CspParameters> 클래스를 사용하여 하드웨어 암호화 디바이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-104">You can use the <xref:System.Security.Cryptography.CspParameters> class to access hardware encryption devices.</span></span> <span data-ttu-id="ecb6c-105">예를 들어 이 클래스를 사용하여 스마트 카드, 하드웨어 난수 생성기 또는 특정 암호화 알고리즘의 하드웨어 구현과 애플리케이션을 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-105">For example, you can use this class to integrate your application with a smart card, a hardware random number generator, or a hardware implementation of a particular cryptographic algorithm.</span></span>  

<span data-ttu-id="ecb6c-106"><xref:System.Security.Cryptography.CspParameters> 클래스는 제대로 설치된 하드웨어 암호화 디바이스에 액세스하는 CSP(암호화 서비스 공급자)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-106">The <xref:System.Security.Cryptography.CspParameters> class creates a cryptographic service provider (CSP) that accesses a properly installed hardware encryption device.</span></span>  <span data-ttu-id="ecb6c-107">레지스트리 편집기(Regedit.exe)를 통해 다음 레지스트리 키를 검사하여 CSP의 가용성을 확인할 수 있습니다. HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-107">You can verify the availability of a CSP by inspecting the following registry key using the Registry Editor (Regedit.exe):  HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span></span>  
  
### <a name="to-sign-data-using-a-key-card"></a><span data-ttu-id="ecb6c-108">키 카드를 사용하여 데이터에 서명하려면</span><span class="sxs-lookup"><span data-stu-id="ecb6c-108">To sign data using a key card</span></span>  
  
1. <span data-ttu-id="ecb6c-109">정수 공급자 형식과 공급자 이름을 생성자에 전달하여 <xref:System.Security.Cryptography.CspParameters> 클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-109">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="ecb6c-110">새로 만든 <xref:System.Security.Cryptography.CspParameters> 개체의 <xref:System.Security.Cryptography.CspParameters.Flags%2A> 속성에 적절한 플래그를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-110">Pass the appropriate flags to the <xref:System.Security.Cryptography.CspParameters.Flags%2A> property of the newly created <xref:System.Security.Cryptography.CspParameters> object.</span></span>  <span data-ttu-id="ecb6c-111">예를 들어 <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> 플래그를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-111">For example, pass the <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> flag.</span></span>  
  
3. <span data-ttu-id="ecb6c-112"><xref:System.Security.Cryptography.CspParameters> 개체를 생성자에 전달하여 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 클래스(예: <xref:System.Security.Cryptography.RSACryptoServiceProvider> 클래스)의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-112">Create a new instance of an <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (for example, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class), passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
4. <span data-ttu-id="ecb6c-113">`Sign` 메서드 중 하나를 사용하여 데이터에 서명하고 `Verify` 메서드 중 하나를 사용하여 데이터를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-113">Sign your data using one of the `Sign` methods and verify your data using one of the `Verify` methods.</span></span>  
  
### <a name="to-generate-a-random-number-using-a-hardware-random-number-generator"></a><span data-ttu-id="ecb6c-114">하드웨어 난수 생성기를 사용하여 난수를 생성하려면</span><span class="sxs-lookup"><span data-stu-id="ecb6c-114">To generate a random number using a hardware random number generator</span></span>  
  
1. <span data-ttu-id="ecb6c-115">정수 공급자 형식과 공급자 이름을 생성자에 전달하여 <xref:System.Security.Cryptography.CspParameters> 클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-115">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="ecb6c-116"><xref:System.Security.Cryptography.CspParameters> 개체를 생성자에 전달하여 <xref:System.Security.Cryptography.RNGCryptoServiceProvider>의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-116">Create a new instance of the <xref:System.Security.Cryptography.RNGCryptoServiceProvider>, passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
3. <span data-ttu-id="ecb6c-117"><xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> 또는 <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> 메서드를 사용하여 난수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-117">Create a random value using the <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> or <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecb6c-118">예제</span><span class="sxs-lookup"><span data-stu-id="ecb6c-118">Example</span></span>

<span data-ttu-id="ecb6c-119">다음 코드 예제에서는 스마트 카드를 사용하여 데이터에 서명하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-119">The following code example demonstrates how to sign data using a smart card.</span></span>  <span data-ttu-id="ecb6c-120">코드 예제에서는 스마트 카드를 노출하는 <xref:System.Security.Cryptography.CspParameters> 개체를 만든 다음 CSP를 사용하여 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 개체를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-120">The code example creates a <xref:System.Security.Cryptography.CspParameters> object that exposes a smart card, and then initializes an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object using the CSP.</span></span>  <span data-ttu-id="ecb6c-121">그런 다음 일부 데이터에 서명하고 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-121">The code example then signs and verifies some data.</span></span>  

<span data-ttu-id="ecb6c-122">S h a 1의 충돌 문제 때문에 SHA256 이상을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-122">Due to collision problems with SHA1, we recommend SHA256 or better.</span></span>
  
[!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
[!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
[!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ecb6c-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ecb6c-123">Compiling the Code</span></span>  
  
- <span data-ttu-id="ecb6c-124"><xref:System> 및 <xref:System.Security.Cryptography> 네임스페이스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-124">Include the <xref:System> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
- <span data-ttu-id="ecb6c-125">스마트 카드 판독기 및 드라이버가 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-125">You must have a smart card reader and drivers installed on your computer.</span></span>  
  
- <span data-ttu-id="ecb6c-126">카드 판독기와 관련된 정보를 사용하여 <xref:System.Security.Cryptography.CspParameters> 개체를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-126">You must initialize the <xref:System.Security.Cryptography.CspParameters> object using information specific to your card reader.</span></span>  <span data-ttu-id="ecb6c-127">자세한 내용은 카드 판독기 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ecb6c-127">For more information, see the documentation of your card reader.</span></span>

## <a name="see-also"></a><span data-ttu-id="ecb6c-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ecb6c-128">See also</span></span>

- [<span data-ttu-id="ecb6c-129">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="ecb6c-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="ecb6c-130">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="ecb6c-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="ecb6c-131">플랫폼 간 암호화</span><span class="sxs-lookup"><span data-stu-id="ecb6c-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="ecb6c-132">ASP.NET Core 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="ecb6c-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
