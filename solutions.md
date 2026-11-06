HTML
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mobile-First Responsive Dashboard</title>
    <meta name="description" content="A mobile-first responsive dashboard layout with adaptive breakpoints using CSS Media Queries.">
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="dashboard-layout">
        <!-- Header -->
        <header class="dash-header">
            <div class="logo">DevPortal</div>
            <div class="user-profile">
                <span>Atim Akhtar</span>
                <div class="avatar">AA</div>
            </div>
        </header>

        <!-- Sidebar Navigation -->
        <aside class="dash-sidebar">
            <nav class="sidebar-nav">
                <ul>
                    <li><a href="#" class="active">Dashboard</a></li>
                    <li><a href="#">Projects</a></li>
                    <li><a href="#">Analytics</a></li>
                    <li><a href="#">Settings</a></li>
                </ul>
            </nav>
        </aside>

        <!-- Main Content Area -->
        <main class="dash-main">
            <div class="welcome-section">
                <h2>Dashboard Overview</h2>
                <p>Welcome back! Here is your system performance and activity summary.</p>
            </div>

            <!-- Statistic Cards Grid -->
            <div class="stats-container">
                <div class="stat-card">
                    <div class="card-icon bg-blue">📁</div>
                    <div class="card-content">
                        <h3>Total Projects</h3>
                        <p class="stat-value">12</p>
                        <span class="trend positive">+2 this month</span>
                    </div>
                </div>

                <div class="stat-card">
                    <div class="card-icon bg-green">👥</div>
                    <div class="card-content">
                        <h3>Active Users</h3>
                        <p class="stat-value">1,429</p>
                        <span class="trend positive">+12% from last week</span>
                    </div>
                </div>

                <div class="stat-card">
                    <div class="card-icon bg-purple">⭐</div>
                    <div class="card-content">
                        <h3>Repository Stars</h3>
                        <p class="stat-value">348</p>
                        <span class="trend positive">+24 today</span>
                    </div>
                </div>

                <div class="stat-card">
                    <div class="card-icon bg-orange">⚠️</div>
                    <div class="card-content">
                        <h3>Pending Issues</h3>
                        <p class="stat-value">3</p>
                        <span class="trend negative">Requires attention</span>
                    </div>
                </div>
            </div>

            <!-- Recent Activity Table Section -->
            <section class="activity-section">
                <div class="section-header">
                    <h3>Recent Submissions</h3>
                    <a href="#" class="view-all">View All</a>
                </div>
                <div class="table-responsive">
                    <table class="activity-table">
                        <thead>
                            <tr>
                                <th>Assignment / Project</th>
                                <th>Category</th>
                                <th>Status</th>
                                <th>Date</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>Assignment 9.1 — Mobile-First Layout</td>
                                <td>Media Queries</td>
                                <td><span class="status-badge success">Completed</span></td>
                                <td>Nov 7, 2026</td>
                            </tr>
                            <tr>
                                <td>Assignment 8.5 — CSS Grid Mini-Project</td>
                                <td>CSS Grid</td>
                                <td><span class="status-badge success">Completed</span></td>
                                <td>Nov 7, 2026</td>
                            </tr>
                            <tr>
                                <td>Assignment 8.4 — Dashboard Grid & Flexbox</td>
                                <td>Grid & Flex</td>
                                <td><span class="status-badge success">Completed</span></td>
                                <td>Nov 7, 2026</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </section>
        </main>
    </div>
</body>
</html>
CSS
/* style.css — Mobile-First Approach */
:root {
    --primary-color: #0284c7;
    --secondary-color: #0f172a;
    --sidebar-bg: #1e293b;
    --bg-color: #f8fafc;
    --surface-color: #ffffff;
    --text-color: #334155;
    --text-muted: #64748b;
    --border-color: #e2e8f0;
    
    --space-sm: 8px;
    --space-md: 16px;
    --space-lg: 24px;
    --space-xl: 32px;
    
    --radius-md: 8px;
    --radius-lg: 12px;
    --shadow-sm: 0 1px 3px rgba(0, 0, 0, 0.05);
    --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.05);
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

body {
    font-family: Arial, sans-serif;
    background-color: var(--bg-color);
    color: var(--text-color);
    line-height: 1.6;
}

/* Base Mobile Layout (Stacked Single Column) */
.dashboard-layout {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

/* Header Styles */
.dash-header {
    background-color: var(--surface-color);
    border-bottom: 1px solid var(--border-color);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: var(--space-md) var(--space-lg);
    position: sticky;
    top: 0;
    z-index: 100;
}

.logo {
    font-size: 1.15rem;
    font-weight: bold;
    color: var(--secondary-color);
}

.user-profile {
    display: flex;
    align-items: center;
    gap: var(--space-sm);
    font-weight: 600;
    font-size: 0.875rem;
}

.avatar {
    width: 32px;
    height: 32px;
    background-color: var(--primary-color);
    color: var(--surface-color);
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 0.75rem;
}

/* Sidebar Navigation (Stacked / Collapsed on Mobile) */
.dash-sidebar {
    background-color: var(--sidebar-bg);
    padding: var(--space-md);
}

.sidebar-nav ul {
    list-style: none;
    display: flex;
    gap: var(--space-sm);
    overflow-x: auto;
    padding-bottom: 4px;
}

.sidebar-nav a {
    display: block;
    color: #94a3b8;
    text-decoration: none;
    font-weight: 500;
    font-size: 0.875rem;
    padding: 6px 12px;
    border-radius: var(--radius-md);
    white-space: nowrap;
    transition: background-color 0.2s ease, color 0.2s ease;
}

.sidebar-nav a:hover,
.sidebar-nav a.active {
    background-color: var(--primary-color);
    color: var(--surface-color);
}

/* Main Content Area */
.dash-main {
    padding: var(--space-md);
    display: flex;
    flex-direction: column;
    gap: var(--space-lg);
    width: 100%;
    overflow-x: hidden;
}

.welcome-section h2 {
    font-size: 1.35rem;
    color: var(--secondary-color);
    margin-bottom: 4px;
}

.welcome-section p {
    color: var(--text-muted);
    font-size: 0.9rem;
}

/* Stats Cards Grid (Mobile First: 1 column) */
.stats-container {
    display: grid;
    grid-template-columns: 1fr;
    gap: var(--space-md);
}

.stat-card {
    background-color: var(--surface-color);
    border: 1px solid var(--border-color);
    border-radius: var(--radius-lg);
    padding: var(--space-md);
    box-shadow: var(--shadow-sm);
    display: flex;
    align-items: center;
    gap: var(--space-md);
}

.card-icon {
    width: 44px;
    height: 44px;
    border-radius: var(--radius-md);
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 1.1rem;
    flex-shrink: 0;
}

.bg-blue { background-color: #e0f2fe; color: #0284c7; }
.bg-green { background-color: #dcfce7; color: #15803d; }
.bg-purple { background-color: #f3e8ff; color: #7e22ce; }
.bg-orange { background-color: #ffedd5; color: #c2410c; }

.card-content {
    display: flex;
    flex-direction: column;
}

.card-content h3 {
    font-size: 0.8rem;
    color: var(--text-muted);
    font-weight: 500;
}

.stat-value {
    font-size: 1.25rem;
    font-weight: bold;
    color: var(--secondary-color);
    margin: 2px 0;
}

.trend {
    font-size: 0.7rem;
    font-weight: bold;
}

.trend.positive { color: #16a34a; }
.trend.negative { color: #dc2626; }

/* Recent Activity Table Section */
.activity-section {
    background-color: var(--surface-color);
    border: 1px solid var(--border-color);
    border-radius: var(--radius-lg);
    padding: var(--space-md);
    box-shadow: var(--shadow-sm);
}

.section-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: var(--space-md);
    border-bottom: 1px solid var(--border-color);
    padding-bottom: var(--space-sm);
}

.section-header h3 {
    font-size: 1.05rem;
    color: var(--secondary-color);
}

.view-all {
    font-size: 0.8rem;
    color: var(--primary-color);
    text-decoration: none;
    font-weight: bold;
}

.table-responsive {
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
}

.activity-table {
    width: 100%;
    border-collapse: collapse;
    text-align: left;
    font-size: 0.85rem;
    min-width: 500px;
}

.activity-table th,
.activity-table td {
    padding: 10px 12px;
    border-bottom: 1px solid var(--border-color);
}

.activity-table th {
    font-weight: 600;
    color: var(--text-muted);
    background-color: #f8fafc;
}

.status-badge {
    font-size: 0.7rem;
    font-weight: bold;
    padding: 3px 6px;
    border-radius: 4px;
    display: inline-block;
}

.status-badge.success {
    background-color: #dcfce7;
    color: #15803d;
}


/* ==========================================
   Breakpoint 1: Tablet View (min-width: 640px)
   ================================---------- */
@media (min-width: 640px) {
    .dash-main {
        padding: var(--space-lg);
    }

    .stats-container {
        grid-template-columns: repeat(2, 1fr);
        gap: var(--space-md);
    }

    .activity-section {
        padding: var(--space-lg);
    }
}


/* ==========================================
   Breakpoint 2: Desktop View (min-width: 1024px)
   ================================---------- */
@media (min-width: 1024px) {
    .dashboard-layout {
        display: grid;
        grid-template-columns: 260px 1fr;
        grid-template-rows: 70px 1fr;
        grid-template-areas:
            "header header"
            "sidebar main";
        min-height: 100vh;
    }

    .dash-header {
        grid-area: header;
        padding: 0 var(--space-xl);
        position: sticky;
    }

    .dash-sidebar {
        grid-area: sidebar;
        padding: var(--space-xl) var(--space-md);
    }

    .sidebar-nav ul {
        flex-direction: column;
        overflow-x: visible;
    }

    .sidebar-nav a {
        padding: var(--space-sm) var(--space-md);
        font-size: 0.95rem;
    }

    .dash-main {
        grid-area: main;
        padding: var(--space-xl);
        gap: var(--space-xl);
    }

    .welcome-section h2 {
        font-size: 1.75rem;
    }

    .stats-container {
        grid-template-columns: repeat(4, 1fr);
        gap: var(--space-lg);
    }

    .stat-card {
        padding: var(--space-lg);
    }

    .activity-table {
        font-size: 0.95rem;
        min-width: 100%;
    }
}