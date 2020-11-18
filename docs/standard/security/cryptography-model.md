---
title: .NET 암호화 모델
description: .NET에서 일반적인 암호화 알고리즘의 구현을 검토 합니다. 개체 상속, 스트림 디자인 & 구성의 확장 가능한 암호화 모델에 대해 알아봅니다.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], model
- encryption [.NET], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: f9ec08992cb8db8f81f11de661612e1b7d15131c
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831119"
---
# <a name="net-cryptography-model"></a><span data-ttu-id="31bcd-104">.NET 암호화 모델</span><span class="sxs-lookup"><span data-stu-id="31bcd-104">.NET Cryptography Model</span></span>

<span data-ttu-id="31bcd-105">.NET에서는 많은 표준 암호화 알고리즘의 구현을 제공 하며 .NET 암호화 모델을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-105">.NET provides implementations of many standard cryptographic algorithms, and the .NET cryptography model is extensible.</span></span>

## <a name="object-inheritance"></a><span data-ttu-id="31bcd-106">개체 상속</span><span class="sxs-lookup"><span data-stu-id="31bcd-106">Object Inheritance</span></span>

<span data-ttu-id="31bcd-107">.NET 암호화 시스템은 파생 클래스 상속의 확장 가능한 패턴을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-107">The .NET cryptography system implements an extensible pattern of derived class inheritance.</span></span> <span data-ttu-id="31bcd-108">계층 구조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-108">The hierarchy is as follows:</span></span>

- <span data-ttu-id="31bcd-109">알고리즘 유형 클래스 (예: <xref:System.Security.Cryptography.SymmetricAlgorithm> , <xref:System.Security.Cryptography.AsymmetricAlgorithm> 또는) <xref:System.Security.Cryptography.HashAlgorithm></span><span class="sxs-lookup"><span data-stu-id="31bcd-109">Algorithm type class, such as <xref:System.Security.Cryptography.SymmetricAlgorithm>,  <xref:System.Security.Cryptography.AsymmetricAlgorithm>, or <xref:System.Security.Cryptography.HashAlgorithm>.</span></span> <span data-ttu-id="31bcd-110">이 수준은 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-110">This level is abstract.</span></span>

- <span data-ttu-id="31bcd-111">알고리즘 형식 클래스에서 상속되는 알고리즘 클래스. 예를 들어 <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA> 또는 <xref:System.Security.Cryptography.ECDiffieHellman>입니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-111">Algorithm class that inherits from an algorithm type class; for example, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA>, or <xref:System.Security.Cryptography.ECDiffieHellman>.</span></span> <span data-ttu-id="31bcd-112">이 수준은 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-112">This level is abstract.</span></span>

- <span data-ttu-id="31bcd-113">알고리즘 클래스에서 상속되는 알고리즘 클래스의 구현. 예를 들어 <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> 또는 <xref:System.Security.Cryptography.ECDiffieHellmanCng>입니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-113">Implementation of an algorithm class that inherits from an algorithm class; for example, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider>, or <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="31bcd-114">이 수준은 완전히 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-114">This level is fully implemented.</span></span>

<span data-ttu-id="31bcd-115">이 패턴의 파생 클래스를 사용 하 여 새 알고리즘 또는 기존 알고리즘의 새 구현을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-115">This pattern of derived classes lets you add a new algorithm or a new implementation of an existing algorithm.</span></span> <span data-ttu-id="31bcd-116">예를 들어 새로운 공용 키 알고리즘을 만들려면 <xref:System.Security.Cryptography.AsymmetricAlgorithm> 클래스에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-116">For example, to create a new public-key algorithm, you would inherit from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class.</span></span> <span data-ttu-id="31bcd-117">특정 알고리즘의 새 구현을 만들려면 해당 알고리즘의 비추상 파생 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-117">To create a new implementation of a specific algorithm, you would create a non-abstract derived class of that algorithm.</span></span>

## <a name="how-algorithms-are-implemented-in-net"></a><span data-ttu-id="31bcd-118">.NET에서 알고리즘을 구현 하는 방법</span><span class="sxs-lookup"><span data-stu-id="31bcd-118">How Algorithms Are Implemented in .NET</span></span>

<span data-ttu-id="31bcd-119">알고리즘에 사용할 수 있는 다양한 구현의 예로 대칭 알고리즘을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="31bcd-119">As an example of the different implementations available for an algorithm, consider symmetric algorithms.</span></span> <span data-ttu-id="31bcd-120">모든 대칭 알고리즘의 기본은, <xref:System.Security.Cryptography.SymmetricAlgorithm> <xref:System.Security.Cryptography.Aes> <xref:System.Security.Cryptography.TripleDES> 및 더 이상 권장 되지 않는 다른 항목에서 상속 되는입니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-120">The base for all symmetric algorithms is <xref:System.Security.Cryptography.SymmetricAlgorithm>, which is inherited by <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.TripleDES>, and others that are no longer recommended.</span></span>

<span data-ttu-id="31bcd-121"><xref:System.Security.Cryptography.Aes> 는, 및에 상속 됩니다 <xref:System.Security.Cryptography.AesCryptoServiceProvider> <xref:System.Security.Cryptography.AesCng> <xref:System.Security.Cryptography.AesManaged> .</span><span class="sxs-lookup"><span data-stu-id="31bcd-121"><xref:System.Security.Cryptography.Aes> is inherited by <xref:System.Security.Cryptography.AesCryptoServiceProvider>, <xref:System.Security.Cryptography.AesCng>, and <xref:System.Security.Cryptography.AesManaged>.</span></span>

<span data-ttu-id="31bcd-122">Windows의 .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="31bcd-122">In .NET Framework on Windows:</span></span>

* <span data-ttu-id="31bcd-123">`*CryptoServiceProvider` 와 같은 알고리즘 클래스는 <xref:System.Security.Cryptography.AesCryptoServiceProvider> 알고리즘의 CAPI (Windows CRYPTOGRAPHY API) 구현을 중심으로 하는 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-123">`*CryptoServiceProvider` algorithm classes, such as <xref:System.Security.Cryptography.AesCryptoServiceProvider>, are wrappers around the Windows Cryptography API (CAPI) implementation of an algorithm.</span></span>
* <span data-ttu-id="31bcd-124">`*Cng` 와 같은 알고리즘 클래스는 <xref:System.Security.Cryptography.ECDiffieHellmanCng> CNG (Windows Cryptography Next generation) 구현을 중심으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-124">`*Cng` algorithm classes, such as <xref:System.Security.Cryptography.ECDiffieHellmanCng>, are wrappers around the Windows Cryptography Next Generation (CNG) implementation.</span></span>
* <span data-ttu-id="31bcd-125">`*Managed` 와 같은 클래스는 <xref:System.Security.Cryptography.AesManaged> 완전히 관리 코드로 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-125">`*Managed` classes, such as <xref:System.Security.Cryptography.AesManaged>, are written entirely in managed code.</span></span> <span data-ttu-id="31bcd-126">`*Managed` 구현은 연방 FIPS (정보 처리 표준)의 인증을 받지 않으며 `*CryptoServiceProvider` 및 래퍼 클래스 보다 느릴 수 있습니다 `*Cng` .</span><span class="sxs-lookup"><span data-stu-id="31bcd-126">`*Managed` implementations are not certified by the Federal Information Processing Standards (FIPS), and may be slower than the `*CryptoServiceProvider` and `*Cng` wrapper classes.</span></span>

<span data-ttu-id="31bcd-127">.NET Core 및 .NET 5 이상 버전에서 모든 구현 클래스 ( `*CryptoServiceProvider` , `*Managed` 및 `*Cng` )는 os (운영 체제) 알고리즘에 대 한 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-127">In .NET Core and .NET 5 and later versions, all implementation classes (`*CryptoServiceProvider`, `*Managed`, and `*Cng`) are wrappers for the operating system (OS) algorithms.</span></span> <span data-ttu-id="31bcd-128">OS 알고리즘이 FIPS 인증 인 경우 .NET은 FIPS 인증 알고리즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-128">If the OS algorithms are FIPS-certified, then .NET uses FIPS-certified algorithms.</span></span> <span data-ttu-id="31bcd-129">자세한 내용은 [플랫폼 간 암호화](cross-platform-cryptography.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="31bcd-129">For more information, see [Cross-Platform Cryptography](cross-platform-cryptography.md).</span></span>

<span data-ttu-id="31bcd-130">대부분의 경우와 같은 알고리즘 구현 클래스를 직접 참조할 필요가 없습니다 `AesCryptoServiceProvider` .</span><span class="sxs-lookup"><span data-stu-id="31bcd-130">In most cases, you don't need to directly reference an algorithm implementation class, such as `AesCryptoServiceProvider`.</span></span> <span data-ttu-id="31bcd-131">일반적으로 필요한 메서드 및 속성은와 같은 기본 알고리즘 클래스에 있습니다 `Aes` .</span><span class="sxs-lookup"><span data-stu-id="31bcd-131">The methods and properties you typically need are on the base algorithm class, such as `Aes`.</span></span> <span data-ttu-id="31bcd-132">기본 알고리즘 클래스에서 팩터리 메서드를 사용 하 여 기본 구현 클래스의 인스턴스를 만들고 기본 알고리즘 클래스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-132">Create an instance of a default implementation class by using a factory method on the base algorithm class, and refer to the base algorithm class.</span></span> <span data-ttu-id="31bcd-133">예를 들어 다음 예제에서 강조 표시 된 코드 줄을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="31bcd-133">For example, see the highlighted line of code in the following example:</span></span>

:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs" highlight="16":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb" highlight="12":::

## <a name="cryptographic-configuration"></a><span data-ttu-id="31bcd-134">암호화 구성</span><span class="sxs-lookup"><span data-stu-id="31bcd-134">Cryptographic Configuration</span></span>

<span data-ttu-id="31bcd-135">암호화 구성을 사용 하면 알고리즘의 특정 구현을 알고리즘 이름으로 확인 하 여 .NET 암호화 클래스의 확장성을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-135">Cryptographic configuration lets you resolve a specific implementation of an algorithm to an algorithm name, allowing extensibility of the .NET cryptography classes.</span></span> <span data-ttu-id="31bcd-136">알고리즘의 고유한 하드웨어 또는 소프트웨어 구현을 추가하고 선택한 알고리즘 이름에 해당 구현을 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-136">You can add your own hardware or software implementation of an algorithm and map the implementation to the algorithm name of your choice.</span></span> <span data-ttu-id="31bcd-137">구성 파일에 알고리즘이 지정되지 않은 경우 기본 설정이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-137">If an algorithm is not specified in the configuration file, the default settings are used.</span></span>

## <a name="choosing-an-algorithm"></a><span data-ttu-id="31bcd-138">알고리즘 선택</span><span class="sxs-lookup"><span data-stu-id="31bcd-138">Choosing an Algorithm</span></span>

<span data-ttu-id="31bcd-139">데이터 무결성, 데이터 프라이버시 또는 키 생성과 같은 다양한 이유로 알고리즘을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-139">You can select an algorithm for different reasons: for example, for data integrity, for data privacy, or to generate a key.</span></span> <span data-ttu-id="31bcd-140">대칭 및 해시 알고리즘은 무결성(변경 차단) 또는 프라이버시(보기 차단)를 위해 데이터를 보호하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-140">Symmetric and hash algorithms are intended for protecting data for either integrity reasons (protect from change) or privacy reasons (protect from viewing).</span></span> <span data-ttu-id="31bcd-141">해시 알고리즘은 주로 데이터 무결성을 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-141">Hash algorithms are used primarily for data integrity.</span></span>

<span data-ttu-id="31bcd-142">애플리케이션에서 권장하는 알고리즘 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="31bcd-142">Here is a list of recommended algorithms by application:</span></span>

- <span data-ttu-id="31bcd-143">데이터 프라이버시:</span><span class="sxs-lookup"><span data-stu-id="31bcd-143">Data privacy:</span></span>
  - <xref:System.Security.Cryptography.Aes>
- <span data-ttu-id="31bcd-144">데이터 무결성:</span><span class="sxs-lookup"><span data-stu-id="31bcd-144">Data integrity:</span></span>
  - <xref:System.Security.Cryptography.HMACSHA256>
  - <xref:System.Security.Cryptography.HMACSHA512>
- <span data-ttu-id="31bcd-145">디지털 서명:</span><span class="sxs-lookup"><span data-stu-id="31bcd-145">Digital signature:</span></span>
  - <xref:System.Security.Cryptography.ECDsa>
  - <xref:System.Security.Cryptography.RSA>
- <span data-ttu-id="31bcd-146">키 교환:</span><span class="sxs-lookup"><span data-stu-id="31bcd-146">Key exchange:</span></span>
  - <xref:System.Security.Cryptography.ECDiffieHellman>
  - <xref:System.Security.Cryptography.RSA>
- <span data-ttu-id="31bcd-147">난수 생성:</span><span class="sxs-lookup"><span data-stu-id="31bcd-147">Random number generation:</span></span>
  - <xref:System.Security.Cryptography.RandomNumberGenerator.Create%2A?displayProperty=nameWithType>
- <span data-ttu-id="31bcd-148">암호에서 키 생성:</span><span class="sxs-lookup"><span data-stu-id="31bcd-148">Generating a key from a password:</span></span>
  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a><span data-ttu-id="31bcd-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31bcd-149">See also</span></span>

- [<span data-ttu-id="31bcd-150">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="31bcd-150">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="31bcd-151">플랫폼 간 암호화</span><span class="sxs-lookup"><span data-stu-id="31bcd-151">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="31bcd-152">ASP.NET Core 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="31bcd-152">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
