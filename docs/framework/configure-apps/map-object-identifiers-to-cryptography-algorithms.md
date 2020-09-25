---
title: 개체 식별자를 암호화 알고리즘에 매핑
description: XML 구성 파일의 y 및 nameEntry 요소를 사용 하 여 .NET의 암호화 알고리즘에 OID (개체 식별자)를 매핑하는 방법을 참조 하세요.
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
ms.openlocfilehash: 5416ddbb766dfde56fa28a3853ed448cc73f25a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189385"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="50de8-103">개체 식별자를 암호화 알고리즘에 매핑</span><span class="sxs-lookup"><span data-stu-id="50de8-103">Mapping Object Identifiers to Cryptography Algorithms</span></span>

<span data-ttu-id="50de8-104">디지털 서명은 한 프로그램에서 다른 프로그램으로 전송 될 때 데이터가 변조 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="50de8-104">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="50de8-105">일반적으로 디지털 서명은 서명할 데이터의 해시에 수치 연산 함수를 적용 하 여 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50de8-105">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="50de8-106">서명할 해시 값의 형식을 지정할 때 일부 디지털 서명 알고리즘은 서식 지정 작업의 일부로 asn.1 (개체 식별자)을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="50de8-106">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="50de8-107">OID는 해시를 계산 하는 데 사용 된 알고리즘을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="50de8-107">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="50de8-108">알고리즘을 개체 식별자에 매핑하여 암호화 메커니즘을 확장 하 여 사용자 지정 알고리즘을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50de8-108">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="50de8-109">다음 예제에서는 새 해시 알고리즘에 개체 식별자를 매핑하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="50de8-109">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="50de8-110">[ \<oidEntry> 요소](./file-schema/cryptography/oidentry-element.md) 는 두 가지 특성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="50de8-110">The [\<oidEntry> element](./file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="50de8-111">**OID** 특성은 개체 식별자 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="50de8-111">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="50de8-112">**Name** 특성은 [ \<nameEntry> 요소의](./file-schema/cryptography/nameentry-element.md) **name** 특성 값입니다.</span><span class="sxs-lookup"><span data-stu-id="50de8-112">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="50de8-113">개체 식별자를 단순 이름에 매핑하기 전에 알고리즘 이름에서 클래스로 매핑되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50de8-113">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50de8-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50de8-114">See also</span></span>

- [<span data-ttu-id="50de8-115">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="50de8-115">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
- [<span data-ttu-id="50de8-116">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="50de8-116">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
