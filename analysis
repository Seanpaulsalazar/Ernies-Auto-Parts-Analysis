import React, { useState } from "react";
import {
  LineChart, Line, BarChart, Bar, XAxis, YAxis, CartesianGrid, Tooltip,
  ResponsiveContainer, PieChart, Pie, Cell, Legend
} from "recharts";

const monthly = [
  { m: "Jan24", v: 12737.24 }, { m: "Feb24", v: 8664.40 }, { m: "Mar24", v: 10164.00 },
  { m: "Apr24", v: 11189.00 }, { m: "May24", v: 10169.59 }, { m: "Jun24", v: 12274.00 },
  { m: "Jul24", v: 14896.00 }, { m: "Aug24", v: 7084.00 }, { m: "Sep24", v: 5965.83 },
  { m: "Oct24", v: 15623.00 }, { m: "Nov24", v: 11216.00 }, { m: "Dec24", v: 5191.00 },
  { m: "Jan25", v: 14600.09 }, { m: "Feb25", v: 9037.15 }, { m: "Mar25", v: 9314.00 },
  { m: "Apr25", v: 9243.21 }, { m: "May25", v: 8341.20 }, { m: "Jun25", v: 8316.00 },
  { m: "Jul25", v: 8670.00 }, { m: "Aug25", v: 4618.00 }, { m: "Sep25", v: 11490.00 },
  { m: "Oct25", v: 10853.00 }, { m: "Nov25", v: 8025.92 }, { m: "Dec25", v: 9283.00 },
  { m: "Jan26", v: 12734.49 }, { m: "Feb26", v: 11094.00 }, { m: "Mar26", v: 17126.00 },
  { m: "Apr26", v: 8826.00 }, { m: "May26", v: 7137.00 }, { m: "Jun26", v: 6959.00 },
];

const yearly = [
  { year: "2024", total: 125174.06 },
  { year: "2025", total: 111791.57 },
  { year: "2026 YTD", total: 63876.49 },
];

const accounts = [
  { name: "Confidential Collision LLC", "2024": 87965.43, "2025": 79139.87, "2026": 51278.49, color: "#E8570A" },
  { name: "5 Stars Automotive", "2024": 30142.80, "2025": 26405.00, "2026": 8304.00, color: "#3E6C9E" },
  { name: "Quality Collision & Motors", "2024": 3219.00, "2025": 1000.00, "2026": 1050.00, color: "#9CA9B7" },
  { name: "Long Beach Collision Ctr", "2024": 0, "2025": 3130.00, "2026": 1144.00, color: "#C9A227" },
  { name: "Other / churned accounts", "2024": 3846.83, "2025": 2116.70, "2026": 2100.00, color: "#5A6472" },
];

const pieData2026 = accounts.map(a => ({ name: a.name, value: a["2026"], color: a.color }));

export default function Report() {
  const [tab, setTab] = useState("overview");

  const totalRevenue = 300842.12;
  const annualizedRun = (63876.49 / 6) * 12;

  return (
    <div style={{
      fontFamily: "'IBM Plex Mono', monospace",
      background: "#181C22",
      color: "#EDEDE7",
      minHeight: "100vh",
      padding: "0",
    }}>
      <style>{`
        @import url('https://fonts.googleapis.com/css2?family=Oswald:wght@400;500;600;700&family=IBM+Plex+Mono:wght@400;500;600&family=Inter:wght@400;500;600&display=swap');
        * { box-sizing: border-box; }
        .display { font-family: 'Oswald', sans-serif; letter-spacing: 0.02em; }
        .body-font { font-family: 'Inter', sans-serif; }
        .tab-btn {
          background: transparent;
          border: none;
          color: #9CA9B7;
          font-family: 'Oswald', sans-serif;
          font-size: 13px;
          letter-spacing: 0.12em;
          text-transform: uppercase;
          padding: 12px 18px;
          cursor: pointer;
          border-bottom: 2px solid transparent;
          transition: all 0.15s ease;
        }
        .tab-btn:hover { color: #EDEDE7; }
        .tab-btn.active { color: #E8570A; border-bottom: 2px solid #E8570A; }
        .card {
          background: #1F242C;
          border: 1px solid #2C333D;
          border-radius: 2px;
        }
        .ticket-edge {
          background: repeating-linear-gradient(90deg, transparent, transparent 6px, #2C333D 6px, #2C333D 12px);
          height: 1px;
        }
        ::selection { background: #E8570A; color: #14181D; }
      `}</style>

      <div style={{ borderBottom: "3px solid #E8570A", padding: "36px 40px 24px" }}>
        <div style={{ display: "flex", justifyContent: "space-between", alignItems: "flex-end", flexWrap: "wrap", gap: 16 }}>
          <div>
            <div style={{ color: "#E8570A", fontSize: 12, letterSpacing: "0.25em", marginBottom: 8 }} className="display">
              ACCOUNT LEDGER · SALES ANALYSIS
            </div>
            <h1 className="display" style={{ fontSize: 42, fontWeight: 700, margin: 0, color: "#F5F3EC" }}>
              ERNIE'S AUTO PARTS
            </h1>
            <div className="body-font" style={{ color: "#9CA9B7", fontSize: 14, marginTop: 6 }}>
              B2B Wholesale Sales Portfolio · Jan 2024 &ndash; Jun 2026
            </div>
          </div>
          <div style={{ textAlign: "right" }} className="body-font">
            <div style={{ fontSize: 11, color: "#5A6472" }}>PREPARED</div>
            <div style={{ fontSize: 14, color: "#EDEDE7" }}>Jul 02, 2026</div>
            <div style={{ fontSize: 11, color: "#5A6472", marginTop: 8 }}>RECORD NO.</div>
            <div style={{ fontSize: 14, color: "#EDEDE7" }}>001&ndash;700 / LEDGER-3YR</div>
          </div>
        </div>
      </div>

      <div style={{ display: "flex", borderBottom: "1px solid #2C333D", padding: "0 40px", background: "#14181D" }}>
        {[
          { id: "overview", label: "Overview" },
          { id: "accounts", label: "Accounts" },
          { id: "trend", label: "Monthly Trend" },
        ].map(t => (
          <button key={t.id} className={`tab-btn ${tab === t.id ? "active" : ""}`} onClick={() => setTab(t.id)}>
            {t.label}
          </button>
        ))}
      </div>

      <div style={{ padding: "32px 40px 60px", maxWidth: 1100, margin: "0 auto" }}>

        {tab === "overview" && (
          <>
            <div style={{ display: "grid", gridTemplateColumns: "repeat(auto-fit, minmax(220px, 1fr))", gap: 16, marginBottom: 32 }}>
              <StatCard label="CUMULATIVE REVENUE" value={`$${totalRevenue.toLocaleString(undefined, { minimumFractionDigits: 2 })}`} accent />
              <StatCard label="MULTI-ACCOUNT PORTFOLIO" value="B2B" sub="built on service quality, not sales volume" />
              <StatCard label="2026 ANNUALIZED RUN RATE" value={`$${Math.round(annualizedRun).toLocaleString()}`} sub="based on Jan–Jun 2026" />
              <StatCard label="PRIORITY ACCOUNT SHARE, 2026" value="80%" sub="Confidential Collision LLC" />
            </div>

            <div className="ticket-edge" style={{ margin: "0 0 32px" }} />

            <div className="card body-font" style={{ padding: 28, marginBottom: 28, lineHeight: 1.7, color: "#C8CDD3", fontSize: 15 }}>
              <div className="display" style={{ color: "#E8570A", fontSize: 13, letterSpacing: "0.15em", marginBottom: 12 }}>
                FINDINGS
              </div>
              Revenue has held steady at roughly $125,000 to $128,000 annually across the full period, though the
              composition beneath that figure has shifted meaningfully. Confidential Collision LLC now accounts for
              close to 80% of 2026 revenue, up from about 70% in 2024, a concentration built entirely through
              sustained service quality rather than active sales effort. Beginning in 2024, I made a deliberate
              tradeoff to hold the account base steady rather than pursue further growth, redirecting that time
              toward completing coursework and preparing for a career in business analytics and consulting.
              Because these accounts are grounded in personal trust rather than a transferable sales process,
              expanding the business further would not have served that longer term goal. Underlying records,
              including sales reports, business permits, and purchase orders, are available for verification.
            </div>

            <div style={{ display: "grid", gridTemplateColumns: "1fr 1fr", gap: 16 }}>
              <div className="card" style={{ padding: 24 }}>
                <SectionLabel>Annual Revenue</SectionLabel>
                <ResponsiveContainer width="100%" height={220}>
                  <BarChart data={yearly}>
                    <CartesianGrid stroke="#2C333D" vertical={false} />
                    <XAxis dataKey="year" tick={{ fill: "#9CA9B7", fontSize: 12 }} axisLine={{ stroke: "#2C333D" }} tickLine={false} />
                    <YAxis tick={{ fill: "#9CA9B7", fontSize: 11 }} axisLine={false} tickLine={false}
                      tickFormatter={(v) => `$${(v / 1000).toFixed(0)}k`} />
                    <Tooltip contentStyle={{ background: "#1F242C", border: "1px solid #2C333D", fontFamily: "IBM Plex Mono" }}
                      formatter={(v) => [`$${v.toLocaleString(undefined, { minimumFractionDigits: 2 })}`, "Revenue"]} />
                    <Bar dataKey="total" fill="#E8570A" radius={[2, 2, 0, 0]} />
                  </BarChart>
                </ResponsiveContainer>
              </div>

              <div className="card" style={{ padding: 24 }}>
                <SectionLabel>2026 Revenue Share by Account</SectionLabel>
                <ResponsiveContainer width="100%" height={220}>
                  <PieChart>
                    <Pie data={pieData2026} dataKey="value" nameKey="name" innerRadius={50} outerRadius={80} paddingAngle={2}>
                      {pieData2026.map((entry, i) => <Cell key={i} fill={entry.color} stroke="#181C22" strokeWidth={2} />)}
                    </Pie>
                    <Tooltip contentStyle={{ background: "#1F242C", border: "1px solid #2C333D", fontFamily: "IBM Plex Mono" }}
                      formatter={(v) => `$${v.toLocaleString(undefined, { minimumFractionDigits: 2 })}`} />
                  </PieChart>
                </ResponsiveContainer>
              </div>
            </div>
          </>
        )}

        {tab === "accounts" && (
          <>
            <SectionLabel>Revenue by Account, Year over Year</SectionLabel>
            <div className="card" style={{ padding: 24, marginBottom: 24 }}>
              <ResponsiveContainer width="100%" height={320}>
                <BarChart data={accounts} layout="vertical" margin={{ left: 20 }}>
                  <CartesianGrid stroke="#2C333D" horizontal={false} />
                  <XAxis type="number" tick={{ fill: "#9CA9B7", fontSize: 11 }} axisLine={false} tickLine={false}
                    tickFormatter={(v) => `$${(v / 1000).toFixed(0)}k`} />
                  <YAxis type="category" dataKey="name" width={190} tick={{ fill: "#EDEDE7", fontSize: 12 }} axisLine={false} tickLine={false} />
                  <Tooltip contentStyle={{ background: "#1F242C", border: "1px solid #2C333D", fontFamily: "IBM Plex Mono" }}
                    formatter={(v) => `$${Number(v).toLocaleString(undefined, { minimumFractionDigits: 2 })}`} />
                  <Legend wrapperStyle={{ fontFamily: "Inter", fontSize: 12, color: "#9CA9B7" }} />
                  <Bar dataKey="2024" fill="#5A6472" radius={[0, 2, 2, 0]} />
                  <Bar dataKey="2025" fill="#3E6C9E" radius={[0, 2, 2, 0]} />
                  <Bar dataKey="2026" fill="#E8570A" radius={[0, 2, 2, 0]} />
                </BarChart>
              </ResponsiveContainer>
            </div>

            <div className="card" style={{ padding: 20 }}>
              <div className="display" style={{ color: "#E8570A", fontSize: 13, letterSpacing: "0.1em", marginBottom: 8 }}>TOP ACCOUNT</div>
              <div className="body-font" style={{ color: "#EDEDE7", fontSize: 15, marginBottom: 4 }}>Confidential Collision LLC</div>
              <div className="body-font" style={{ color: "#9CA9B7", fontSize: 13, lineHeight: 1.6 }}>
                $87,965 in 2024, $79,140 in 2025, and $51,278 through June 2026, on pace for roughly $102,500 this
                year. This level of concentration developed organically, through consistent service over multiple
                years rather than deliberate account expansion.
              </div>
            </div>
          </>
        )}

        {tab === "trend" && (
          <>
            <SectionLabel>Monthly Revenue, Jan 2024 &ndash; Jun 2026</SectionLabel>
            <div className="card" style={{ padding: 24 }}>
              <ResponsiveContainer width="100%" height={340}>
                <LineChart data={monthly}>
                  <CartesianGrid stroke="#2C333D" vertical={false} />
                  <XAxis dataKey="m" tick={{ fill: "#9CA9B7", fontSize: 10 }} axisLine={{ stroke: "#2C333D" }} tickLine={false}
                    interval={2} />
                  <YAxis tick={{ fill: "#9CA9B7", fontSize: 11 }} axisLine={false} tickLine={false}
                    tickFormatter={(v) => `$${(v / 1000).toFixed(0)}k`} />
                  <Tooltip contentStyle={{ background: "#1F242C", border: "1px solid #2C333D", fontFamily: "IBM Plex Mono" }}
                    formatter={(v) => [`$${Number(v).toLocaleString(undefined, { minimumFractionDigits: 2 })}`, "Revenue"]} />
                  <Line type="monotone" dataKey="v" stroke="#E8570A" strokeWidth={2} dot={{ r: 2, fill: "#E8570A" }} />
                </LineChart>
              </ResponsiveContainer>
            </div>
            <div className="body-font" style={{ color: "#5A6472", fontSize: 12, marginTop: 12 }}>
              Monthly revenue before tax, aggregated from sales trend and terms reports. March 2026 ($17,126) is the
              strongest month in the dataset; August 2025 ($4,618) is the weakest.
            </div>
          </>
        )}
      </div>

      <div style={{ borderTop: "1px solid #2C333D", padding: "20px 40px", textAlign: "center" }} className="body-font">
        <span style={{ color: "#5A6472", fontSize: 11, letterSpacing: "0.1em" }}>
          ERNIE'S AUTO PARTS &middot; INTERNAL SALES LEDGER ANALYSIS &middot; PREPARED FOR PORTFOLIO USE
        </span>
      </div>
    </div>
  );
}

function StatCard({ label, value, sub, accent }) {
  return (
    <div className="card" style={{ padding: "18px 20px", borderLeft: accent ? "3px solid #E8570A" : "1px solid #2C333D" }}>
      <div className="display" style={{ fontSize: 11, letterSpacing: "0.12em", color: "#9CA9B7", marginBottom: 8 }}>
        {label}
      </div>
      <div className="display" style={{ fontSize: 26, fontWeight: 600, color: accent ? "#E8570A" : "#F5F3EC" }}>
        {value}
      </div>
      {sub && <div className="body-font" style={{ fontSize: 12, color: "#5A6472", marginTop: 4 }}>{sub}</div>}
    </div>
  );
}

function SectionLabel({ children }) {
  return (
    <div className="display" style={{ color: "#E8570A", fontSize: 13, letterSpacing: "0.15em", marginBottom: 14 }}>
      {children.toString().toUpperCase()}
    </div>
  );
}
