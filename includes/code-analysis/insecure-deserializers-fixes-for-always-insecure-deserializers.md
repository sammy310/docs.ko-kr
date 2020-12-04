---
author: dotpaul
ms.author: paulming
ms.date: 05/01/2019
ms.topic: include
ms.openlocfilehash: cf944ae9ca200d34a1f0f32e68bf3aee73a9500a
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592141"
---
- <span data-ttu-id="62907-101">가능 하면 보안 serializer를 대신 사용 하 고 **공격자가 deserialize 할 임의의 형식을 지정할 수 없도록** 합니다.</span><span class="sxs-lookup"><span data-stu-id="62907-101">If possible, use a secure serializer instead, and **don't allow an attacker to specify an arbitrary type to deserialize**.</span></span> <span data-ttu-id="62907-102">몇 가지 안전한 serializer는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="62907-102">Some safer serializers include:</span></span>

  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <span data-ttu-id="62907-103"><xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> -사용 하지 마세요 <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="62907-103"><xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> - Never use <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType>.</span></span> <span data-ttu-id="62907-104">형식 확인자를 사용 해야 하는 경우 deserialize 된 형식을 예상 목록으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="62907-104">If you must use a type resolver, restrict deserialized types to an expected list.</span></span>
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - <span data-ttu-id="62907-105">Newtonsoft.json Json.NET-TypeNameHandling를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="62907-105">Newtonsoft Json.NET - Use TypeNameHandling.None.</span></span> <span data-ttu-id="62907-106">TypeNameHandling에 다른 값을 사용 해야 하는 경우 사용자 지정 ISerializationBinder를 사용 하 여 deserialize 된 형식을 예상 목록으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="62907-106">If you must use another value for TypeNameHandling, restrict deserialized types to an expected list with a custom ISerializationBinder.</span></span>
  - <span data-ttu-id="62907-107">프로토콜 버퍼</span><span class="sxs-lookup"><span data-stu-id="62907-107">Protocol Buffers</span></span>

- <span data-ttu-id="62907-108">Serialize 된 데이터를 변조 방지로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="62907-108">Make the serialized data tamper-proof.</span></span> <span data-ttu-id="62907-109">Serialization 후 직렬화 된 데이터를 암호화 하 여 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="62907-109">After serialization, cryptographically sign the serialized data.</span></span> <span data-ttu-id="62907-110">Deserialization 전에 암호화 서명 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="62907-110">Before deserialization, validate the cryptographic signature.</span></span> <span data-ttu-id="62907-111">암호화 키가 공개 되지 않도록 보호 하 고 키 회전을 설계 합니다.</span><span class="sxs-lookup"><span data-stu-id="62907-111">Protect the cryptographic key from being disclosed and design for key rotations.</span></span>
