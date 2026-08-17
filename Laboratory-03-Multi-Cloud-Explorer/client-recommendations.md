# Cloud Platform Recommendations

## Client A – Startup Company
**Recommended Platform:** AWS

This startup has a limited budget but expects rapid growth, which makes AWS a strong fit because of its generous free tier and true pay-as-you-go pricing, so the company only pays for what it actually uses in the early stages. AWS also scales extremely well, meaning the startup won't need to migrate to a different provider as its user base grows. Its large ecosystem of managed services also lets a small team move fast without needing to manage heavy infrastructure themselves.

**Services the client could use:**
- AWS Lambda (serverless compute for the mobile app backend)
- Amazon DynamoDB (scalable NoSQL database)
- AWS Amplify (fast front-end and mobile app deployment)

## Client B – University
**Recommended Platform:** Microsoft Azure

Since the university already relies on Windows Server, Microsoft 365, and Active Directory, Azure is the natural choice because it integrates directly with the tools they already use, reducing the complexity of migration. Azure Active Directory (Microsoft Entra ID) can extend the university's existing identity system into the cloud without rebuilding it from scratch. This also means staff and students can keep using familiar Microsoft tools while the university gradually shifts services to the cloud.

**Services the client could use:**
- Microsoft Entra ID (extending existing Active Directory to the cloud)
- Azure Virtual Desktop (remote access to university applications)
- Azure SQL Database (cloud-hosted database for student and academic records)

## Client C – AI Research Company
**Recommended Platform:** Google Cloud Platform (GCP)

This company builds AI and machine learning applications that require high-performance computing, which lines up directly with GCP's strengths. GCP offers TPUs (Tensor Processing Units) specifically designed to accelerate machine learning workloads faster than standard hardware. Its data analytics and AI tooling, such as Vertex AI, also gives researchers an end-to-end platform for building, training, and deploying models.

**Services the client could use:**
- Vertex AI (building and deploying machine learning models)
- Compute Engine with TPUs/GPUs (high-performance computing for training models)
- BigQuery (analyzing large research datasets)

## Client D – Global E-Commerce Company
**Recommended Platform:** AWS

This company needs highly available infrastructure with automatic scaling to serve customers worldwide, which fits AWS's global reach and mature infrastructure. With Availability Zones spread across many regions, AWS can keep the platform online even if one data center experiences issues. AWS also has strong content delivery and auto-scaling tools that are well suited to handling unpredictable traffic spikes common in e-commerce, such as during sales events.

**Services the client could use:**
- Amazon EC2 Auto Scaling (automatically adjusts server capacity based on demand)
- Amazon CloudFront (content delivery network for fast global access)
- Amazon Route 53 (reliable, low-latency DNS routing)

---

## Checkpoint 6 – Multi-Cloud Decision Matrix
Create a simple decision matrix recommending the best cloud provider for different business needs

| **Business Requirement** | **Recommended Platform** | **Justification** |
|---|---|---|
| Startup Company | AWS | Generous free tier and pay-as-you-go pricing supports growth without heavy upfront cost. |
| Enterprise Organization | AWS | Widest service catalog and most mature, proven infrastructure for large-scale operations. |
| Microsoft Environment | Azure | Deepest integration with Windows Server, Active Directory, and Microsoft 365. |
| AI / Machine Learning | GCP | Purpose-built AI tools (Vertex AI, TPUs) and strong data analytics capabilities. |
| Kubernetes Deployment | GCP | Google created Kubernetes, making GKE the most mature managed Kubernetes service. |
| Global Web Application | AWS | Extensive global infrastructure with CDN and DNS services for high availability. |
