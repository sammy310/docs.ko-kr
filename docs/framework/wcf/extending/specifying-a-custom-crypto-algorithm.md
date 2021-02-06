---
description: '자세한 정보: 사용자 지정 암호화 알고리즘 지정'
title: 사용자 지정 암호화 알고리즘 지정
ms.date: 03/30/2017
ms.assetid: d662a305-8e09-451d-9a59-b0f12b012f1d
ms.openlocfilehash: 4d4cb525b46b33a0d0df8dd6a3db9e9fafe84f8f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643971"
---
# <a name="specifying-a-custom-crypto-algorithm"></a><span data-ttu-id="8c66b-103">사용자 지정 암호화 알고리즘 지정</span><span class="sxs-lookup"><span data-stu-id="8c66b-103">Specifying a Custom Crypto Algorithm</span></span>

<span data-ttu-id="8c66b-104">WCF를 통해 데이터를 암호화하거나 디지털 서명을 연산화할 때 사용할 사용자 지정 암호화 알고리즘을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-104">WCF allows you to specify a custom crypto algorithm to use when encrypting data or computing digital signatures.</span></span> <span data-ttu-id="8c66b-105">이렇게 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-105">This is done by the following steps:</span></span>  
  
1. <span data-ttu-id="8c66b-106"><xref:System.ServiceModel.Security.SecurityAlgorithmSuite>에서 클래스를 파생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-106">Derive a class from <xref:System.ServiceModel.Security.SecurityAlgorithmSuite></span></span>  
  
2. <span data-ttu-id="8c66b-107">알고리즘을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-107">Register the algorithm</span></span>  
  
3. <span data-ttu-id="8c66b-108"><xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 파생 클래스로 바인딩을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-108">Configure the binding with the <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-derived class.</span></span>  
  
## <a name="derive-a-class-from-securityalgorithmsuite"></a><span data-ttu-id="8c66b-109">SecurityAlgorithmSuite에서 클래스를 파생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-109">Derive a class from SecurityAlgorithmSuite</span></span>  

 <span data-ttu-id="8c66b-110"><xref:System.ServiceModel.Security.SecurityAlgorithmSuite>는 다양한 보안 관련 작업을 수행할 때 사용할 알고리즘을 지정할 수 있도록 하는 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-110">The <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> is an abstract base class that allows you to specify the algorithm to use when performing various security related operations.</span></span> <span data-ttu-id="8c66b-111">예를 들어 디지털 서명의 해시를 계산하거나 메시지를 암호화하는 작업을 수행할 때 활용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-111">For example, computing a hash for a digital signature or encrypting a message.</span></span> <span data-ttu-id="8c66b-112">다음 코드에서는 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>에서 클래스를 파생하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-112">The following code shows how to derive a class from <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>:</span></span>  
  
```csharp  
public class MyCustomAlgorithmSuite : SecurityAlgorithmSuite  
    {  
        public override string DefaultAsymmetricKeyWrapAlgorithm  
        {  
            get { return SecurityAlgorithms.RsaOaepKeyWrap; }  
        }  
  
        public override string DefaultAsymmetricSignatureAlgorithm  
        {  
            get { return SecurityAlgorithms.RsaSha1Signature; }  
        }  
  
        public override string DefaultCanonicalizationAlgorithm  
        {  
            get { return SecurityAlgorithms.ExclusiveC14n; ; }  
        }  
  
        public override string DefaultDigestAlgorithm  
        {  
            get { return SecurityAlgorithms.MyCustomHashAlgorithm; }  
        }  
  
        public override string DefaultEncryptionAlgorithm  
        {  
            get { return SecurityAlgorithms.Aes128Encryption; }  
        }  
  
        public override int DefaultEncryptionKeyDerivationLength  
        {  
            get { return 128; }  
        }  
  
        public override int DefaultSignatureKeyDerivationLength  
        {  
            get { return 128; }  
        }  
  
        public override int DefaultSymmetricKeyLength  
        {  
            get { return 128; }  
        }  
  
        public override string DefaultSymmetricKeyWrapAlgorithm  
        {  
            get { return SecurityAlgorithms.Aes128Encryption; }  
        }  
  
        public override string DefaultSymmetricSignatureAlgorithm  
        {  
            get { return SecurityAlgorithms.HmacSha1Signature; }  
        }  
  
        public override bool IsAsymmetricKeyLengthSupported(int length)  
        {  
            return length >= 1024 && length <= 4096;  
        }  
  
        public override bool IsSymmetricKeyLengthSupported(int length)  
        {  
            return length >= 128 && length <= 256;  
        }  
    }  
```  
  
## <a name="register-the-custom-algorithm"></a><span data-ttu-id="8c66b-113">사용자 지정 알고리즘을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-113">Register the Custom Algorithm</span></span>  

 <span data-ttu-id="8c66b-114">등록은 구성 파일이나 명령적 코드에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-114">Registration can be done in a configuration file or in imperative code.</span></span> <span data-ttu-id="8c66b-115">암호화 서비스 공급자를 구현하는 클래스와 별칭 간의 매핑을 만들어 사용자 지정 알고리즘을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-115">Registering a custom algorithm is done by creating a mapping between a class that implements a crypto service provider and an alias.</span></span> <span data-ttu-id="8c66b-116">그런 다음 별칭은 WCF 서비스의 바인딩에서 알고리즘을 지정할 때 사용되는 URI에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-116">The alias is then mapped to a URI which is used when specifying the algorithm in the WCF service’s binding.</span></span> <span data-ttu-id="8c66b-117">다음 구성 코드 조각은 구성에서 사용자 지정 알고리즘을 등록하는 방법을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-117">The following configuration snippet illustrates how to register a custom algorithm in config:</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
           <cryptoClasses>  
              <cryptoClass SHA256CSP="System.Security.Cryptography.SHA256CryptoServiceProvider, System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
           </cryptoClasses>  
           <nameEntry name="http://contoso.com/CustomAlgorithms/CustomHashAlgorithm"  
              class="SHA256CSP" />  
           </cryptoNameMapping>  
        </cryptographySettings>  
    </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="8c66b-118"><> 요소 아래에 있는 섹션에서는 `cryptoClasses` 은 sha256cryptoserviceprovider와 별칭 "SHA256CSP" 사이에 매핑을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-118">The section under the <`cryptoClasses`> element creates the mapping between the SHA256CryptoServiceProvider and the alias "SHA256CSP".</span></span> <span data-ttu-id="8c66b-119"><`nameEntry`> 요소는 "SHA256CSP" 별칭과 지정 된 URL 간 매핑을 만듭니다 `http://contoso.com/CustomAlgorithms/CustomHashAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="8c66b-119">The <`nameEntry`> element creates the mapping between the "SHA256CSP" alias and the specified URL `http://contoso.com/CustomAlgorithms/CustomHashAlgorithm`.</span></span>  
  
 <span data-ttu-id="8c66b-120">코드로 사용자 지정 알고리즘을 등록하려면 <xref:System.Security.Cryptography.CryptoConfig.AddAlgorithm(System.Type,System.String[])> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-120">To register the custom algorithm in code use the <xref:System.Security.Cryptography.CryptoConfig.AddAlgorithm(System.Type,System.String[])> method.</span></span> <span data-ttu-id="8c66b-121">이 메서드는 두 매핑을 모두 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-121">This method creates both mappings.</span></span> <span data-ttu-id="8c66b-122">다음 예제에서는 이 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-122">The following example shows how to call this method:</span></span>  
  
```csharp
// Register the custom URI string defined for the hashAlgorithm in MyCustomAlgorithmSuite class to create the
// SHA256CryptoServiceProvider hash algorithm object.  
CryptoConfig.AddAlgorithm(typeof(SHA256CryptoServiceProvider), "http://contoso.com/CustomAlgorithms/CustomHashAlgorithm");  
```  
  
## <a name="configure-the-binding"></a><span data-ttu-id="8c66b-123">바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="8c66b-123">Configure the Binding</span></span>  

 <span data-ttu-id="8c66b-124">다음 코드 조각과 같이 바인딩 설정에서 사용자 지정 <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> 파생 클래스를 지정하여 바인딩을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8c66b-124">You configure the binding by specifying the custom <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-derived class in the binding settings as shown in the following code snippet:</span></span>  
  
```csharp  
WSHttpBinding binding = new WSHttpBinding();  
            binding.Security.Message.AlgorithmSuite = new MyCustomAlgorithmSuite();  
```  
  
 <span data-ttu-id="8c66b-125">전체 코드 예제를 보려면 [WCF 보안 샘플의 암호화 민첩성](../samples/cryptographic-agility-in-wcf-security.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8c66b-125">For a complete code example, see the [Cryptographic Agility in WCF Security](../samples/cryptographic-agility-in-wcf-security.md) sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c66b-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c66b-126">See also</span></span>

- [<span data-ttu-id="8c66b-127">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8c66b-127">Securing Services and Clients</span></span>](../feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="8c66b-128">서비스에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="8c66b-128">Securing Services</span></span>](../securing-services.md)
- [<span data-ttu-id="8c66b-129">보안 개요</span><span class="sxs-lookup"><span data-stu-id="8c66b-129">Security Overview</span></span>](../feature-details/security-overview.md)
- [<span data-ttu-id="8c66b-130">보안 개념</span><span class="sxs-lookup"><span data-stu-id="8c66b-130">Security Concepts</span></span>](../feature-details/security-concepts.md)
