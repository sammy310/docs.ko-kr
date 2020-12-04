---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 9235f1bcda7529b71aef542d3a49da08a9d4b59e
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592129"
---
<span data-ttu-id="1ed5b-101">안전 하지 않은 데이터는 deserialize 할 때 취약 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed5b-101">Insecure deserializers are vulnerable when deserializing untrusted data.</span></span> <span data-ttu-id="1ed5b-102">공격자는 예기치 않은 형식을 포함 하도록 serialize 된 데이터를 수정 하 여 악의적인 부작용으로 개체를 주입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed5b-102">An attacker could modify the serialized data to include unexpected types to inject objects with malicious side effects.</span></span> <span data-ttu-id="1ed5b-103">예를 들어, 안전 하지 않은 역직렬 변환기에 대 한 공격은 기본 운영 체제에서 명령을 실행 하거나, 네트워크를 통해 통신 하거나, 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed5b-103">An attack against an insecure deserializer could, for example, execute commands on the underlying operating system, communicate over the network, or delete files.</span></span>
