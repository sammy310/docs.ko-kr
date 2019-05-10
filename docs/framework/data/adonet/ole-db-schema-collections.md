---
title: OLE DB 스키마 컬렉션
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6c3441e86d4c5267418cf8002ba17d539c464d5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645892"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="8c94d-102">OLE DB 스키마 컬렉션</span><span class="sxs-lookup"><span data-stu-id="8c94d-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="8c94d-103">이 단원에서는 Microsoft SQL Server, Oracle 및 Microsoft Jet용 OLE DB 공급자에서 지원하는 스키마 컬렉션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8c94d-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="8c94d-104">Microsoft SQL Server OLE DB 공급자</span><span class="sxs-lookup"><span data-stu-id="8c94d-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="8c94d-105">Microsoft SQL Server OLE DB Driver에서는 공통 스키마 컬렉션 외에도 다음과 같은 특정 스키마 컬렉션을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8c94d-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="8c94d-106">Tables</span><span class="sxs-lookup"><span data-stu-id="8c94d-106">Tables</span></span>  
  
- <span data-ttu-id="8c94d-107">Columns</span><span class="sxs-lookup"><span data-stu-id="8c94d-107">Columns</span></span>  
  
- <span data-ttu-id="8c94d-108">절차</span><span class="sxs-lookup"><span data-stu-id="8c94d-108">Procedures</span></span>  
  
- <span data-ttu-id="8c94d-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8c94d-109">ProcedureParameters</span></span>  
  
- <span data-ttu-id="8c94d-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="8c94d-110">Catalog</span></span>  
  
- <span data-ttu-id="8c94d-111">인덱스</span><span class="sxs-lookup"><span data-stu-id="8c94d-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="8c94d-112">Tables</span><span class="sxs-lookup"><span data-stu-id="8c94d-112">Tables</span></span>  
  
|<span data-ttu-id="8c94d-113">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-113">ColumnName</span></span>|<span data-ttu-id="8c94d-114">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-115">TABLE_CATALOG</span></span>|<span data-ttu-id="8c94d-116">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-116">String</span></span>|  
|<span data-ttu-id="8c94d-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="8c94d-118">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-118">String</span></span>|  
|<span data-ttu-id="8c94d-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-119">TABLE_NAME</span></span>|<span data-ttu-id="8c94d-120">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-120">String</span></span>|  
|<span data-ttu-id="8c94d-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-121">TABLE_TYPE</span></span>|<span data-ttu-id="8c94d-122">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-122">String</span></span>|  
|<span data-ttu-id="8c94d-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-123">TABLE_GUID</span></span>|<span data-ttu-id="8c94d-124">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-124">Guid</span></span>|  
|<span data-ttu-id="8c94d-125">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-125">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-126">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-126">String</span></span>|  
|<span data-ttu-id="8c94d-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="8c94d-127">TABLE_PROPID</span></span>|<span data-ttu-id="8c94d-128">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-128">Int64</span></span>|  
|<span data-ttu-id="8c94d-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8c94d-129">DATE_CREATED</span></span>|<span data-ttu-id="8c94d-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-130">DateTime</span></span>|  
|<span data-ttu-id="8c94d-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8c94d-131">DATE_MODIFIED</span></span>|<span data-ttu-id="8c94d-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="8c94d-133">Columns</span><span class="sxs-lookup"><span data-stu-id="8c94d-133">Columns</span></span>  
  
|<span data-ttu-id="8c94d-134">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-134">ColumnName</span></span>|<span data-ttu-id="8c94d-135">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-136">TABLE_CATALOG</span></span>|<span data-ttu-id="8c94d-137">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-137">String</span></span>|  
|<span data-ttu-id="8c94d-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="8c94d-139">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-139">String</span></span>|  
|<span data-ttu-id="8c94d-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-140">TABLE_NAME</span></span>|<span data-ttu-id="8c94d-141">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-141">String</span></span>|  
|<span data-ttu-id="8c94d-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-142">COLUMN_NAME</span></span>|<span data-ttu-id="8c94d-143">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-143">String</span></span>|  
|<span data-ttu-id="8c94d-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-144">COLUMN_GUID</span></span>|<span data-ttu-id="8c94d-145">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-145">Guid</span></span>|  
|<span data-ttu-id="8c94d-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8c94d-146">COLUMN_PROPID</span></span>|<span data-ttu-id="8c94d-147">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-147">Int64</span></span>|  
|<span data-ttu-id="8c94d-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="8c94d-149">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-149">Int64</span></span>|  
|<span data-ttu-id="8c94d-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="8c94d-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="8c94d-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-151">Boolean</span></span>|  
|<span data-ttu-id="8c94d-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="8c94d-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="8c94d-153">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-153">String</span></span>|  
|<span data-ttu-id="8c94d-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="8c94d-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="8c94d-155">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-155">Int64</span></span>|  
|<span data-ttu-id="8c94d-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8c94d-156">IS_NULLABLE</span></span>|<span data-ttu-id="8c94d-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-157">Boolean</span></span>|  
|<span data-ttu-id="8c94d-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-158">DATA_TYPE</span></span>|<span data-ttu-id="8c94d-159">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-159">Int32</span></span>|  
|<span data-ttu-id="8c94d-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-160">TYPE_GUID</span></span>|<span data-ttu-id="8c94d-161">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-161">Guid</span></span>|  
|<span data-ttu-id="8c94d-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8c94d-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="8c94d-163">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-163">Int64</span></span>|  
|<span data-ttu-id="8c94d-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8c94d-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="8c94d-165">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-165">Int64</span></span>|  
|<span data-ttu-id="8c94d-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8c94d-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="8c94d-167">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-167">Int32</span></span>|  
|<span data-ttu-id="8c94d-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="8c94d-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="8c94d-169">Int16</span><span class="sxs-lookup"><span data-stu-id="8c94d-169">Int16</span></span>|  
|<span data-ttu-id="8c94d-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8c94d-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="8c94d-171">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-171">Int64</span></span>|  
|<span data-ttu-id="8c94d-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="8c94d-173">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-173">String</span></span>|  
|<span data-ttu-id="8c94d-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="8c94d-175">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-175">String</span></span>|  
|<span data-ttu-id="8c94d-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="8c94d-177">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-177">String</span></span>|  
|<span data-ttu-id="8c94d-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="8c94d-179">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-179">String</span></span>|  
|<span data-ttu-id="8c94d-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="8c94d-181">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-181">String</span></span>|  
|<span data-ttu-id="8c94d-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-182">COLLATION_NAME</span></span>|<span data-ttu-id="8c94d-183">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-183">String</span></span>|  
|<span data-ttu-id="8c94d-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="8c94d-185">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-185">String</span></span>|  
|<span data-ttu-id="8c94d-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="8c94d-187">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-187">String</span></span>|  
|<span data-ttu-id="8c94d-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-188">DOMAIN_NAME</span></span>|<span data-ttu-id="8c94d-189">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-189">String</span></span>|  
|<span data-ttu-id="8c94d-190">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-190">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-191">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-191">String</span></span>|  
|<span data-ttu-id="8c94d-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="8c94d-192">COLUMN_LCID</span></span>|<span data-ttu-id="8c94d-193">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-193">Int32</span></span>|  
|<span data-ttu-id="8c94d-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="8c94d-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="8c94d-195">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-195">Int32</span></span>|  
|<span data-ttu-id="8c94d-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="8c94d-196">COLUMN_SORTID</span></span>|<span data-ttu-id="8c94d-197">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-197">Int32</span></span>|  
|<span data-ttu-id="8c94d-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="8c94d-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="8c94d-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="8c94d-199">Byte[]</span></span>|  
|<span data-ttu-id="8c94d-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="8c94d-200">IS_COMPUTED</span></span>|<span data-ttu-id="8c94d-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="8c94d-202">절차</span><span class="sxs-lookup"><span data-stu-id="8c94d-202">Procedures</span></span>  
  
|<span data-ttu-id="8c94d-203">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-203">ColumnName</span></span>|<span data-ttu-id="8c94d-204">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="8c94d-206">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-206">String</span></span>|  
|<span data-ttu-id="8c94d-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="8c94d-208">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-208">String</span></span>|  
|<span data-ttu-id="8c94d-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="8c94d-210">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-210">String</span></span>|  
|<span data-ttu-id="8c94d-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="8c94d-212">Int16</span><span class="sxs-lookup"><span data-stu-id="8c94d-212">Int16</span></span>|  
|<span data-ttu-id="8c94d-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="8c94d-214">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-214">String</span></span>|  
|<span data-ttu-id="8c94d-215">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-215">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-216">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-216">String</span></span>|  
|<span data-ttu-id="8c94d-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8c94d-217">DATE_CREATED</span></span>|<span data-ttu-id="8c94d-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-218">DateTime</span></span>|  
|<span data-ttu-id="8c94d-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8c94d-219">DATE_MODIFIED</span></span>|<span data-ttu-id="8c94d-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="8c94d-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8c94d-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="8c94d-222">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-222">ColumnName</span></span>|<span data-ttu-id="8c94d-223">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="8c94d-225">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-225">String</span></span>|  
|<span data-ttu-id="8c94d-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="8c94d-227">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-227">String</span></span>|  
|<span data-ttu-id="8c94d-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="8c94d-229">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-229">String</span></span>|  
|<span data-ttu-id="8c94d-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-230">PARAMETER_NAME</span></span>|<span data-ttu-id="8c94d-231">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-231">String</span></span>|  
|<span data-ttu-id="8c94d-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="8c94d-233">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-233">Int32</span></span>|  
|<span data-ttu-id="8c94d-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="8c94d-235">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-235">Int32</span></span>|  
|<span data-ttu-id="8c94d-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="8c94d-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="8c94d-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-237">Boolean</span></span>|  
|<span data-ttu-id="8c94d-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="8c94d-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="8c94d-239">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-239">String</span></span>|  
|<span data-ttu-id="8c94d-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8c94d-240">IS_NULLABLE</span></span>|<span data-ttu-id="8c94d-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-241">Boolean</span></span>|  
|<span data-ttu-id="8c94d-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-242">DATA_TYPE</span></span>|<span data-ttu-id="8c94d-243">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-243">Int32</span></span>|  
|<span data-ttu-id="8c94d-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8c94d-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="8c94d-245">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-245">Int64</span></span>|  
|<span data-ttu-id="8c94d-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8c94d-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="8c94d-247">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-247">Int64</span></span>|  
|<span data-ttu-id="8c94d-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8c94d-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="8c94d-249">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-249">Int32</span></span>|  
|<span data-ttu-id="8c94d-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="8c94d-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="8c94d-251">Int16</span><span class="sxs-lookup"><span data-stu-id="8c94d-251">Int16</span></span>|  
|<span data-ttu-id="8c94d-252">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-252">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-253">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-253">String</span></span>|  
|<span data-ttu-id="8c94d-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-254">TYPE_NAME</span></span>|<span data-ttu-id="8c94d-255">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-255">String</span></span>|  
|<span data-ttu-id="8c94d-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="8c94d-257">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="8c94d-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="8c94d-258">Catalog</span></span>  
  
|<span data-ttu-id="8c94d-259">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-259">ColumnName</span></span>|<span data-ttu-id="8c94d-260">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-261">CATALOG_NAME</span></span>|<span data-ttu-id="8c94d-262">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-262">String</span></span>|  
|<span data-ttu-id="8c94d-263">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-263">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-264">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="8c94d-265">인덱스</span><span class="sxs-lookup"><span data-stu-id="8c94d-265">Indexes</span></span>  
  
|<span data-ttu-id="8c94d-266">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-266">ColumnName</span></span>|<span data-ttu-id="8c94d-267">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-268">TABLE_CATALOG</span></span>|<span data-ttu-id="8c94d-269">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-269">String</span></span>|  
|<span data-ttu-id="8c94d-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="8c94d-271">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-271">String</span></span>|  
|<span data-ttu-id="8c94d-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-272">TABLE_NAME</span></span>|<span data-ttu-id="8c94d-273">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-273">String</span></span>|  
|<span data-ttu-id="8c94d-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-274">INDEX_CATALOG</span></span>|<span data-ttu-id="8c94d-275">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-275">String</span></span>|  
|<span data-ttu-id="8c94d-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="8c94d-277">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-277">String</span></span>|  
|<span data-ttu-id="8c94d-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-278">INDEX_NAME</span></span>|<span data-ttu-id="8c94d-279">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-279">String</span></span>|  
|<span data-ttu-id="8c94d-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="8c94d-280">PRIMARY_KEY</span></span>|<span data-ttu-id="8c94d-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-281">Boolean</span></span>|  
|<span data-ttu-id="8c94d-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="8c94d-282">UNIQUE</span></span>|<span data-ttu-id="8c94d-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-283">Boolean</span></span>|  
|<span data-ttu-id="8c94d-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="8c94d-284">CLUSTERED</span></span>|<span data-ttu-id="8c94d-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-285">Boolean</span></span>|  
|<span data-ttu-id="8c94d-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-286">TYPE</span></span>|<span data-ttu-id="8c94d-287">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-287">Int32</span></span>|  
|<span data-ttu-id="8c94d-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="8c94d-288">FILL_FACTOR</span></span>|<span data-ttu-id="8c94d-289">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-289">Int32</span></span>|  
|<span data-ttu-id="8c94d-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="8c94d-290">INITIAL_SIZE</span></span>|<span data-ttu-id="8c94d-291">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-291">Int32</span></span>|  
|<span data-ttu-id="8c94d-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="8c94d-292">NULLS</span></span>|<span data-ttu-id="8c94d-293">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-293">Int32</span></span>|  
|<span data-ttu-id="8c94d-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="8c94d-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="8c94d-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-295">Boolean</span></span>|  
|<span data-ttu-id="8c94d-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="8c94d-296">AUTO_UPDATE</span></span>|<span data-ttu-id="8c94d-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-297">Boolean</span></span>|  
|<span data-ttu-id="8c94d-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="8c94d-298">NULL_COLLATION</span></span>|<span data-ttu-id="8c94d-299">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-299">Int32</span></span>|  
|<span data-ttu-id="8c94d-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="8c94d-301">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-301">Int64</span></span>|  
|<span data-ttu-id="8c94d-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-302">COLUMN_NAME</span></span>|<span data-ttu-id="8c94d-303">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-303">String</span></span>|  
|<span data-ttu-id="8c94d-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-304">COLUMN_GUID</span></span>|<span data-ttu-id="8c94d-305">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-305">Guid</span></span>|  
|<span data-ttu-id="8c94d-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8c94d-306">COLUMN_PROPID</span></span>|<span data-ttu-id="8c94d-307">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-307">Int64</span></span>|  
|<span data-ttu-id="8c94d-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="8c94d-308">COLLATION</span></span>|<span data-ttu-id="8c94d-309">Int16</span><span class="sxs-lookup"><span data-stu-id="8c94d-309">Int16</span></span>|  
|<span data-ttu-id="8c94d-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="8c94d-310">CARDINALITY</span></span>|<span data-ttu-id="8c94d-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="8c94d-311">Decimal</span></span>|  
|<span data-ttu-id="8c94d-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="8c94d-312">PAGES</span></span>|<span data-ttu-id="8c94d-313">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-313">Int32</span></span>|  
|<span data-ttu-id="8c94d-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-314">FILTER_CONDITION</span></span>|<span data-ttu-id="8c94d-315">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-315">String</span></span>|  
|<span data-ttu-id="8c94d-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="8c94d-316">INTEGRATED</span></span>|<span data-ttu-id="8c94d-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="8c94d-318">Microsoft Oracle OLE DB    </span><span class="sxs-lookup"><span data-stu-id="8c94d-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="8c94d-319">Microsoft Oracle OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="8c94d-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="8c94d-320">Tables</span><span class="sxs-lookup"><span data-stu-id="8c94d-320">Tables</span></span>  
  
- <span data-ttu-id="8c94d-321">Columns</span><span class="sxs-lookup"><span data-stu-id="8c94d-321">Columns</span></span>  
  
- <span data-ttu-id="8c94d-322">절차</span><span class="sxs-lookup"><span data-stu-id="8c94d-322">Procedures</span></span>  
  
- <span data-ttu-id="8c94d-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8c94d-323">ProcedureColumns</span></span>  
  
- <span data-ttu-id="8c94d-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8c94d-324">ProcedureParameters</span></span>  
  
- <span data-ttu-id="8c94d-325">보기</span><span class="sxs-lookup"><span data-stu-id="8c94d-325">Views</span></span>  
  
- <span data-ttu-id="8c94d-326">인덱스</span><span class="sxs-lookup"><span data-stu-id="8c94d-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="8c94d-327">Tables</span><span class="sxs-lookup"><span data-stu-id="8c94d-327">Tables</span></span>  
  
|<span data-ttu-id="8c94d-328">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-328">ColumnName</span></span>|<span data-ttu-id="8c94d-329">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-330">TABLE_CATALOG</span></span>|<span data-ttu-id="8c94d-331">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-331">String</span></span>|  
|<span data-ttu-id="8c94d-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="8c94d-333">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-333">String</span></span>|  
|<span data-ttu-id="8c94d-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-334">TABLE_NAME</span></span>|<span data-ttu-id="8c94d-335">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-335">String</span></span>|  
|<span data-ttu-id="8c94d-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-336">TABLE_TYPE</span></span>|<span data-ttu-id="8c94d-337">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-337">String</span></span>|  
|<span data-ttu-id="8c94d-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-338">TABLE_GUID</span></span>|<span data-ttu-id="8c94d-339">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-339">Guid</span></span>|  
|<span data-ttu-id="8c94d-340">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-340">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-341">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-341">String</span></span>|  
|<span data-ttu-id="8c94d-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="8c94d-342">TABLE_PROPID</span></span>|<span data-ttu-id="8c94d-343">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-343">Int64</span></span>|  
|<span data-ttu-id="8c94d-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8c94d-344">DATE_CREATED</span></span>|<span data-ttu-id="8c94d-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-345">DateTime</span></span>|  
|<span data-ttu-id="8c94d-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8c94d-346">DATE_MODIFIED</span></span>|<span data-ttu-id="8c94d-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="8c94d-348">Columns</span><span class="sxs-lookup"><span data-stu-id="8c94d-348">Columns</span></span>  
  
|<span data-ttu-id="8c94d-349">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-349">ColumnName</span></span>|<span data-ttu-id="8c94d-350">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-351">TABLE_CATALOG</span></span>|<span data-ttu-id="8c94d-352">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-352">String</span></span>|  
|<span data-ttu-id="8c94d-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="8c94d-354">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-354">String</span></span>|  
|<span data-ttu-id="8c94d-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-355">TABLE_NAME</span></span>|<span data-ttu-id="8c94d-356">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-356">String</span></span>|  
|<span data-ttu-id="8c94d-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-357">COLUMN_NAME</span></span>|<span data-ttu-id="8c94d-358">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-358">String</span></span>|  
|<span data-ttu-id="8c94d-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-359">COLUMN_GUID</span></span>|<span data-ttu-id="8c94d-360">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-360">Guid</span></span>|  
|<span data-ttu-id="8c94d-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8c94d-361">COLUMN_PROPID</span></span>|<span data-ttu-id="8c94d-362">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-362">Int64</span></span>|  
|<span data-ttu-id="8c94d-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="8c94d-364">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-364">Int64</span></span>|  
|<span data-ttu-id="8c94d-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="8c94d-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="8c94d-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-366">Boolean</span></span>|  
|<span data-ttu-id="8c94d-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="8c94d-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="8c94d-368">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-368">String</span></span>|  
|<span data-ttu-id="8c94d-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="8c94d-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="8c94d-370">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-370">Int64</span></span>|  
|<span data-ttu-id="8c94d-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8c94d-371">IS_NULLABLE</span></span>|<span data-ttu-id="8c94d-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-372">Boolean</span></span>|  
|<span data-ttu-id="8c94d-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-373">DATA_TYPE</span></span>|<span data-ttu-id="8c94d-374">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-374">Int32</span></span>|  
|<span data-ttu-id="8c94d-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-375">TYPE_GUID</span></span>|<span data-ttu-id="8c94d-376">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-376">Guid</span></span>|  
|<span data-ttu-id="8c94d-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8c94d-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="8c94d-378">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-378">Int64</span></span>|  
|<span data-ttu-id="8c94d-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8c94d-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="8c94d-380">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-380">Int64</span></span>|  
|<span data-ttu-id="8c94d-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8c94d-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="8c94d-382">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-382">Int32</span></span>|  
|<span data-ttu-id="8c94d-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="8c94d-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="8c94d-384">Int16</span><span class="sxs-lookup"><span data-stu-id="8c94d-384">Int16</span></span>|  
|<span data-ttu-id="8c94d-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8c94d-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="8c94d-386">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-386">Int64</span></span>|  
|<span data-ttu-id="8c94d-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="8c94d-388">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-388">String</span></span>|  
|<span data-ttu-id="8c94d-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="8c94d-390">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-390">String</span></span>|  
|<span data-ttu-id="8c94d-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="8c94d-392">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-392">String</span></span>|  
|<span data-ttu-id="8c94d-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="8c94d-394">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-394">String</span></span>|  
|<span data-ttu-id="8c94d-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="8c94d-396">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-396">String</span></span>|  
|<span data-ttu-id="8c94d-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-397">COLLATION_NAME</span></span>|<span data-ttu-id="8c94d-398">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-398">String</span></span>|  
|<span data-ttu-id="8c94d-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="8c94d-400">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-400">String</span></span>|  
|<span data-ttu-id="8c94d-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="8c94d-402">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-402">String</span></span>|  
|<span data-ttu-id="8c94d-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-403">DOMAIN_NAME</span></span>|<span data-ttu-id="8c94d-404">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-404">String</span></span>|  
|<span data-ttu-id="8c94d-405">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-405">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-406">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="8c94d-407">절차</span><span class="sxs-lookup"><span data-stu-id="8c94d-407">Procedures</span></span>  
  
|<span data-ttu-id="8c94d-408">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-408">ColumnName</span></span>|<span data-ttu-id="8c94d-409">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="8c94d-411">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-411">String</span></span>|  
|<span data-ttu-id="8c94d-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="8c94d-413">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-413">String</span></span>|  
|<span data-ttu-id="8c94d-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="8c94d-415">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-415">String</span></span>|  
|<span data-ttu-id="8c94d-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="8c94d-417">Int16</span><span class="sxs-lookup"><span data-stu-id="8c94d-417">Int16</span></span>|  
|<span data-ttu-id="8c94d-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="8c94d-419">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-419">String</span></span>|  
|<span data-ttu-id="8c94d-420">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-420">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-421">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-421">String</span></span>|  
|<span data-ttu-id="8c94d-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8c94d-422">DATE_CREATED</span></span>|<span data-ttu-id="8c94d-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-423">DateTime</span></span>|  
|<span data-ttu-id="8c94d-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8c94d-424">DATE_MODIFIED</span></span>|<span data-ttu-id="8c94d-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="8c94d-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8c94d-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="8c94d-427">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-427">ColumnName</span></span>|<span data-ttu-id="8c94d-428">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="8c94d-430">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-430">String</span></span>|  
|<span data-ttu-id="8c94d-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="8c94d-432">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-432">String</span></span>|  
|<span data-ttu-id="8c94d-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="8c94d-434">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-434">String</span></span>|  
|<span data-ttu-id="8c94d-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-435">COLUMN_NAME</span></span>|<span data-ttu-id="8c94d-436">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-436">String</span></span>|  
|<span data-ttu-id="8c94d-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-437">COLUMN_GUID</span></span>|<span data-ttu-id="8c94d-438">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-438">Guid</span></span>|  
|<span data-ttu-id="8c94d-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8c94d-439">COLUMN_PROPID</span></span>|<span data-ttu-id="8c94d-440">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-440">Int64</span></span>|  
|<span data-ttu-id="8c94d-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="8c94d-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="8c94d-442">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-442">Int64</span></span>|  
|<span data-ttu-id="8c94d-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="8c94d-444">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-444">Int64</span></span>|  
|<span data-ttu-id="8c94d-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8c94d-445">IS_NULLABLE</span></span>|<span data-ttu-id="8c94d-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-446">Boolean</span></span>|  
|<span data-ttu-id="8c94d-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-447">DATA_TYPE</span></span>|<span data-ttu-id="8c94d-448">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-448">Int32</span></span>|  
|<span data-ttu-id="8c94d-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-449">TYPE_GUID</span></span>|<span data-ttu-id="8c94d-450">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-450">Guid</span></span>|  
|<span data-ttu-id="8c94d-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8c94d-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="8c94d-452">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-452">Int64</span></span>|  
|<span data-ttu-id="8c94d-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8c94d-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="8c94d-454">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-454">Int64</span></span>|  
|<span data-ttu-id="8c94d-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8c94d-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="8c94d-456">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-456">Int32</span></span>|  
|<span data-ttu-id="8c94d-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="8c94d-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="8c94d-458">Int16</span><span class="sxs-lookup"><span data-stu-id="8c94d-458">Int16</span></span>|  
|<span data-ttu-id="8c94d-459">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-459">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-460">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-460">String</span></span>|  
|<span data-ttu-id="8c94d-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="8c94d-461">OVERLOAD</span></span>|<span data-ttu-id="8c94d-462">Int16</span><span class="sxs-lookup"><span data-stu-id="8c94d-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="8c94d-463">보기</span><span class="sxs-lookup"><span data-stu-id="8c94d-463">Views</span></span>  
  
|<span data-ttu-id="8c94d-464">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-464">ColumnName</span></span>|<span data-ttu-id="8c94d-465">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-466">TABLE_CATALOG</span></span>|<span data-ttu-id="8c94d-467">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-467">String</span></span>|  
|<span data-ttu-id="8c94d-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="8c94d-469">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-469">String</span></span>|  
|<span data-ttu-id="8c94d-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-470">TABLE_NAME</span></span>|<span data-ttu-id="8c94d-471">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-471">String</span></span>|  
|<span data-ttu-id="8c94d-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="8c94d-473">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-473">String</span></span>|  
|<span data-ttu-id="8c94d-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="8c94d-474">CHECK_OPTION</span></span>|<span data-ttu-id="8c94d-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-475">Boolean</span></span>|  
|<span data-ttu-id="8c94d-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="8c94d-476">IS_UPDATABLE</span></span>|<span data-ttu-id="8c94d-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-477">Boolean</span></span>|  
|<span data-ttu-id="8c94d-478">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-478">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-479">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-479">String</span></span>|  
|<span data-ttu-id="8c94d-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8c94d-480">DATE_CREATED</span></span>|<span data-ttu-id="8c94d-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-481">DateTime</span></span>|  
|<span data-ttu-id="8c94d-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8c94d-482">DATE_MODIFIED</span></span>|<span data-ttu-id="8c94d-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="8c94d-484">인덱스</span><span class="sxs-lookup"><span data-stu-id="8c94d-484">Indexes</span></span>  
  
|<span data-ttu-id="8c94d-485">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-485">ColumnName</span></span>|<span data-ttu-id="8c94d-486">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-487">TABLE_CATALOG</span></span>|<span data-ttu-id="8c94d-488">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-488">String</span></span>|  
|<span data-ttu-id="8c94d-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="8c94d-490">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-490">String</span></span>|  
|<span data-ttu-id="8c94d-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-491">TABLE_NAME</span></span>|<span data-ttu-id="8c94d-492">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-492">String</span></span>|  
|<span data-ttu-id="8c94d-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-493">INDEX_CATALOG</span></span>|<span data-ttu-id="8c94d-494">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-494">String</span></span>|  
|<span data-ttu-id="8c94d-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="8c94d-496">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-496">String</span></span>|  
|<span data-ttu-id="8c94d-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-497">INDEX_NAME</span></span>|<span data-ttu-id="8c94d-498">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-498">String</span></span>|  
|<span data-ttu-id="8c94d-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="8c94d-499">PRIMARY_KEY</span></span>|<span data-ttu-id="8c94d-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-500">Boolean</span></span>|  
|<span data-ttu-id="8c94d-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="8c94d-501">UNIQUE</span></span>|<span data-ttu-id="8c94d-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-502">Boolean</span></span>|  
|<span data-ttu-id="8c94d-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="8c94d-503">CLUSTERED</span></span>|<span data-ttu-id="8c94d-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-504">Boolean</span></span>|  
|<span data-ttu-id="8c94d-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-505">TYPE</span></span>|<span data-ttu-id="8c94d-506">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-506">Int32</span></span>|  
|<span data-ttu-id="8c94d-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="8c94d-507">FILL_FACTOR</span></span>|<span data-ttu-id="8c94d-508">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-508">Int32</span></span>|  
|<span data-ttu-id="8c94d-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="8c94d-509">INITIAL_SIZE</span></span>|<span data-ttu-id="8c94d-510">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-510">Int32</span></span>|  
|<span data-ttu-id="8c94d-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="8c94d-511">NULLS</span></span>|<span data-ttu-id="8c94d-512">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-512">Int32</span></span>|  
|<span data-ttu-id="8c94d-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="8c94d-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="8c94d-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-514">Boolean</span></span>|  
|<span data-ttu-id="8c94d-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="8c94d-515">AUTO_UPDATE</span></span>|<span data-ttu-id="8c94d-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-516">Boolean</span></span>|  
|<span data-ttu-id="8c94d-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="8c94d-517">NULL_COLLATION</span></span>|<span data-ttu-id="8c94d-518">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-518">Int32</span></span>|  
|<span data-ttu-id="8c94d-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="8c94d-520">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-520">Int64</span></span>|  
|<span data-ttu-id="8c94d-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-521">COLUMN_NAME</span></span>|<span data-ttu-id="8c94d-522">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-522">String</span></span>|  
|<span data-ttu-id="8c94d-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-523">COLUMN_GUID</span></span>|<span data-ttu-id="8c94d-524">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-524">Guid</span></span>|  
|<span data-ttu-id="8c94d-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8c94d-525">COLUMN_PROPID</span></span>|<span data-ttu-id="8c94d-526">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-526">Int64</span></span>|  
|<span data-ttu-id="8c94d-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="8c94d-527">COLLATION</span></span>|<span data-ttu-id="8c94d-528">Int16</span><span class="sxs-lookup"><span data-stu-id="8c94d-528">Int16</span></span>|  
|<span data-ttu-id="8c94d-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="8c94d-529">CARDINALITY</span></span>|<span data-ttu-id="8c94d-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="8c94d-530">Decimal</span></span>|  
|<span data-ttu-id="8c94d-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="8c94d-531">PAGES</span></span>|<span data-ttu-id="8c94d-532">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-532">Int32</span></span>|  
|<span data-ttu-id="8c94d-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-533">FILTER_CONDITION</span></span>|<span data-ttu-id="8c94d-534">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-534">String</span></span>|  
|<span data-ttu-id="8c94d-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="8c94d-535">INTEGRATED</span></span>|<span data-ttu-id="8c94d-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="8c94d-537">Microsoft Jet OLE DB    </span><span class="sxs-lookup"><span data-stu-id="8c94d-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="8c94d-538">Microsoft Jet OLE DB Driver                                             .</span><span class="sxs-lookup"><span data-stu-id="8c94d-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
- <span data-ttu-id="8c94d-539">Tables</span><span class="sxs-lookup"><span data-stu-id="8c94d-539">Tables</span></span>  
  
- <span data-ttu-id="8c94d-540">Columns</span><span class="sxs-lookup"><span data-stu-id="8c94d-540">Columns</span></span>  
  
- <span data-ttu-id="8c94d-541">절차</span><span class="sxs-lookup"><span data-stu-id="8c94d-541">Procedures</span></span>  
  
- <span data-ttu-id="8c94d-542">보기</span><span class="sxs-lookup"><span data-stu-id="8c94d-542">Views</span></span>  
  
- <span data-ttu-id="8c94d-543">인덱스</span><span class="sxs-lookup"><span data-stu-id="8c94d-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="8c94d-544">Tables</span><span class="sxs-lookup"><span data-stu-id="8c94d-544">Tables</span></span>  
  
|<span data-ttu-id="8c94d-545">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-545">ColumnName</span></span>|<span data-ttu-id="8c94d-546">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-547">TABLE_CATALOG</span></span>|<span data-ttu-id="8c94d-548">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-548">String</span></span>|  
|<span data-ttu-id="8c94d-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="8c94d-550">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-550">String</span></span>|  
|<span data-ttu-id="8c94d-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-551">TABLE_NAME</span></span>|<span data-ttu-id="8c94d-552">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-552">String</span></span>|  
|<span data-ttu-id="8c94d-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-553">TABLE_TYPE</span></span>|<span data-ttu-id="8c94d-554">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-554">String</span></span>|  
|<span data-ttu-id="8c94d-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-555">TABLE_GUID</span></span>|<span data-ttu-id="8c94d-556">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-556">Guid</span></span>|  
|<span data-ttu-id="8c94d-557">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-557">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-558">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-558">String</span></span>|  
|<span data-ttu-id="8c94d-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="8c94d-559">TABLE_PROPID</span></span>|<span data-ttu-id="8c94d-560">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-560">Int64</span></span>|  
|<span data-ttu-id="8c94d-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8c94d-561">DATE_CREATED</span></span>|<span data-ttu-id="8c94d-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-562">DateTime</span></span>|  
|<span data-ttu-id="8c94d-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8c94d-563">DATE_MODIFIED</span></span>|<span data-ttu-id="8c94d-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="8c94d-565">Columns</span><span class="sxs-lookup"><span data-stu-id="8c94d-565">Columns</span></span>  
  
|<span data-ttu-id="8c94d-566">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-566">ColumnName</span></span>|<span data-ttu-id="8c94d-567">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-568">TABLE_CATALOG</span></span>|<span data-ttu-id="8c94d-569">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-569">String</span></span>|  
|<span data-ttu-id="8c94d-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="8c94d-571">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-571">String</span></span>|  
|<span data-ttu-id="8c94d-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-572">TABLE_NAME</span></span>|<span data-ttu-id="8c94d-573">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-573">String</span></span>|  
|<span data-ttu-id="8c94d-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-574">COLUMN_NAME</span></span>|<span data-ttu-id="8c94d-575">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-575">String</span></span>|  
|<span data-ttu-id="8c94d-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-576">COLUMN_GUID</span></span>|<span data-ttu-id="8c94d-577">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-577">Guid</span></span>|  
|<span data-ttu-id="8c94d-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8c94d-578">COLUMN_PROPID</span></span>|<span data-ttu-id="8c94d-579">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-579">Int64</span></span>|  
|<span data-ttu-id="8c94d-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="8c94d-581">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-581">Int64</span></span>|  
|<span data-ttu-id="8c94d-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="8c94d-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="8c94d-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-583">Boolean</span></span>|  
|<span data-ttu-id="8c94d-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="8c94d-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="8c94d-585">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-585">String</span></span>|  
|<span data-ttu-id="8c94d-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="8c94d-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="8c94d-587">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-587">Int64</span></span>|  
|<span data-ttu-id="8c94d-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8c94d-588">IS_NULLABLE</span></span>|<span data-ttu-id="8c94d-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-589">Boolean</span></span>|  
|<span data-ttu-id="8c94d-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-590">DATA_TYPE</span></span>|<span data-ttu-id="8c94d-591">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-591">Int32</span></span>|  
|<span data-ttu-id="8c94d-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-592">TYPE_GUID</span></span>|<span data-ttu-id="8c94d-593">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-593">Guid</span></span>|  
|<span data-ttu-id="8c94d-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8c94d-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="8c94d-595">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-595">Int64</span></span>|  
|<span data-ttu-id="8c94d-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8c94d-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="8c94d-597">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-597">Int64</span></span>|  
|<span data-ttu-id="8c94d-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8c94d-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="8c94d-599">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-599">Int32</span></span>|  
|<span data-ttu-id="8c94d-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="8c94d-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="8c94d-601">Int16</span><span class="sxs-lookup"><span data-stu-id="8c94d-601">Int16</span></span>|  
|<span data-ttu-id="8c94d-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8c94d-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="8c94d-603">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-603">Int64</span></span>|  
|<span data-ttu-id="8c94d-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="8c94d-605">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-605">String</span></span>|  
|<span data-ttu-id="8c94d-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="8c94d-607">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-607">String</span></span>|  
|<span data-ttu-id="8c94d-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="8c94d-609">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-609">String</span></span>|  
|<span data-ttu-id="8c94d-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="8c94d-611">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-611">String</span></span>|  
|<span data-ttu-id="8c94d-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="8c94d-613">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-613">String</span></span>|  
|<span data-ttu-id="8c94d-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-614">COLLATION_NAME</span></span>|<span data-ttu-id="8c94d-615">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-615">String</span></span>|  
|<span data-ttu-id="8c94d-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="8c94d-617">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-617">String</span></span>|  
|<span data-ttu-id="8c94d-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="8c94d-619">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-619">String</span></span>|  
|<span data-ttu-id="8c94d-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-620">DOMAIN_NAME</span></span>|<span data-ttu-id="8c94d-621">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-621">String</span></span>|  
|<span data-ttu-id="8c94d-622">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-622">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-623">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="8c94d-624">절차</span><span class="sxs-lookup"><span data-stu-id="8c94d-624">Procedures</span></span>  
  
|<span data-ttu-id="8c94d-625">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-625">ColumnName</span></span>|<span data-ttu-id="8c94d-626">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="8c94d-628">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-628">String</span></span>|  
|<span data-ttu-id="8c94d-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="8c94d-630">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-630">String</span></span>|  
|<span data-ttu-id="8c94d-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="8c94d-632">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-632">String</span></span>|  
|<span data-ttu-id="8c94d-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="8c94d-634">Int16</span><span class="sxs-lookup"><span data-stu-id="8c94d-634">Int16</span></span>|  
|<span data-ttu-id="8c94d-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="8c94d-636">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-636">String</span></span>|  
|<span data-ttu-id="8c94d-637">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-637">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-638">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-638">String</span></span>|  
|<span data-ttu-id="8c94d-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8c94d-639">DATE_CREATED</span></span>|<span data-ttu-id="8c94d-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-640">DateTime</span></span>|  
|<span data-ttu-id="8c94d-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8c94d-641">DATE_MODIFIED</span></span>|<span data-ttu-id="8c94d-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="8c94d-643">보기</span><span class="sxs-lookup"><span data-stu-id="8c94d-643">Views</span></span>  
  
|<span data-ttu-id="8c94d-644">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-644">ColumnName</span></span>|<span data-ttu-id="8c94d-645">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-646">TABLE_CATALOG</span></span>|<span data-ttu-id="8c94d-647">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-647">String</span></span>|  
|<span data-ttu-id="8c94d-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="8c94d-649">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-649">String</span></span>|  
|<span data-ttu-id="8c94d-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-650">TABLE_NAME</span></span>|<span data-ttu-id="8c94d-651">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-651">String</span></span>|  
|<span data-ttu-id="8c94d-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="8c94d-653">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-653">String</span></span>|  
|<span data-ttu-id="8c94d-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="8c94d-654">CHECK_OPTION</span></span>|<span data-ttu-id="8c94d-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-655">Boolean</span></span>|  
|<span data-ttu-id="8c94d-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="8c94d-656">IS_UPDATABLE</span></span>|<span data-ttu-id="8c94d-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-657">Boolean</span></span>|  
|<span data-ttu-id="8c94d-658">설명</span><span class="sxs-lookup"><span data-stu-id="8c94d-658">DESCRIPTION</span></span>|<span data-ttu-id="8c94d-659">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-659">String</span></span>|  
|<span data-ttu-id="8c94d-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8c94d-660">DATE_CREATED</span></span>|<span data-ttu-id="8c94d-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-661">DateTime</span></span>|  
|<span data-ttu-id="8c94d-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8c94d-662">DATE_MODIFIED</span></span>|<span data-ttu-id="8c94d-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="8c94d-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="8c94d-664">인덱스</span><span class="sxs-lookup"><span data-stu-id="8c94d-664">Indexes</span></span>  
  
|<span data-ttu-id="8c94d-665">열 이름</span><span class="sxs-lookup"><span data-stu-id="8c94d-665">ColumnName</span></span>|<span data-ttu-id="8c94d-666">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8c94d-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8c94d-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-667">TABLE_CATALOG</span></span>|<span data-ttu-id="8c94d-668">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-668">String</span></span>|  
|<span data-ttu-id="8c94d-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="8c94d-670">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-670">String</span></span>|  
|<span data-ttu-id="8c94d-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-671">TABLE_NAME</span></span>|<span data-ttu-id="8c94d-672">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-672">String</span></span>|  
|<span data-ttu-id="8c94d-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8c94d-673">INDEX_CATALOG</span></span>|<span data-ttu-id="8c94d-674">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-674">String</span></span>|  
|<span data-ttu-id="8c94d-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8c94d-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="8c94d-676">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-676">String</span></span>|  
|<span data-ttu-id="8c94d-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-677">INDEX_NAME</span></span>|<span data-ttu-id="8c94d-678">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-678">String</span></span>|  
|<span data-ttu-id="8c94d-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="8c94d-679">PRIMARY_KEY</span></span>|<span data-ttu-id="8c94d-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-680">Boolean</span></span>|  
|<span data-ttu-id="8c94d-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="8c94d-681">UNIQUE</span></span>|<span data-ttu-id="8c94d-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-682">Boolean</span></span>|  
|<span data-ttu-id="8c94d-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="8c94d-683">CLUSTERED</span></span>|<span data-ttu-id="8c94d-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-684">Boolean</span></span>|  
|<span data-ttu-id="8c94d-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="8c94d-685">TYPE</span></span>|<span data-ttu-id="8c94d-686">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-686">Int32</span></span>|  
|<span data-ttu-id="8c94d-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="8c94d-687">FILL_FACTOR</span></span>|<span data-ttu-id="8c94d-688">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-688">Int32</span></span>|  
|<span data-ttu-id="8c94d-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="8c94d-689">INITIAL_SIZE</span></span>|<span data-ttu-id="8c94d-690">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-690">Int32</span></span>|  
|<span data-ttu-id="8c94d-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="8c94d-691">NULLS</span></span>|<span data-ttu-id="8c94d-692">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-692">Int32</span></span>|  
|<span data-ttu-id="8c94d-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="8c94d-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="8c94d-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-694">Boolean</span></span>|  
|<span data-ttu-id="8c94d-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="8c94d-695">AUTO_UPDATE</span></span>|<span data-ttu-id="8c94d-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-696">Boolean</span></span>|  
|<span data-ttu-id="8c94d-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="8c94d-697">NULL_COLLATION</span></span>|<span data-ttu-id="8c94d-698">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-698">Int32</span></span>|  
|<span data-ttu-id="8c94d-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="8c94d-700">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-700">Int64</span></span>|  
|<span data-ttu-id="8c94d-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8c94d-701">COLUMN_NAME</span></span>|<span data-ttu-id="8c94d-702">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-702">String</span></span>|  
|<span data-ttu-id="8c94d-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8c94d-703">COLUMN_GUID</span></span>|<span data-ttu-id="8c94d-704">Guid</span><span class="sxs-lookup"><span data-stu-id="8c94d-704">Guid</span></span>|  
|<span data-ttu-id="8c94d-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8c94d-705">COLUMN_PROPID</span></span>|<span data-ttu-id="8c94d-706">Int64</span><span class="sxs-lookup"><span data-stu-id="8c94d-706">Int64</span></span>|  
|<span data-ttu-id="8c94d-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="8c94d-707">COLLATION</span></span>|<span data-ttu-id="8c94d-708">Int16</span><span class="sxs-lookup"><span data-stu-id="8c94d-708">Int16</span></span>|  
|<span data-ttu-id="8c94d-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="8c94d-709">CARDINALITY</span></span>|<span data-ttu-id="8c94d-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="8c94d-710">Decimal</span></span>|  
|<span data-ttu-id="8c94d-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="8c94d-711">PAGES</span></span>|<span data-ttu-id="8c94d-712">Int32</span><span class="sxs-lookup"><span data-stu-id="8c94d-712">Int32</span></span>|  
|<span data-ttu-id="8c94d-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="8c94d-713">FILTER_CONDITION</span></span>|<span data-ttu-id="8c94d-714">문자열</span><span class="sxs-lookup"><span data-stu-id="8c94d-714">String</span></span>|  
|<span data-ttu-id="8c94d-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="8c94d-715">INTEGRATED</span></span>|<span data-ttu-id="8c94d-716">Boolean</span><span class="sxs-lookup"><span data-stu-id="8c94d-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c94d-717">참고자료</span><span class="sxs-lookup"><span data-stu-id="8c94d-717">See also</span></span>

- [<span data-ttu-id="8c94d-718">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="8c94d-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
