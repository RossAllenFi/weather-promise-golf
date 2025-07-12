
import streamlit as st

st.set_page_config(page_title="Weather Promise Golf Pricing", layout="centered")

st.title("⛳ Weather Promise™ Golf Pricing Model")

# Input sliders
price = st.slider("Protection Price ($)", 5.0, 40.0, 19.99, 0.50)
trigger_rate = st.slider("Trigger Rate (%)", 0.0, 100.0, 33.5, 0.5)
admin_cost = st.slider("Admin Cost ($)", 0.0, 10.0, 2.0, 0.25)
payout = st.slider("Payout Amount ($)", 10.0, 200.0, 80.0, 1.0)

# Calculations
trigger_prob = trigger_rate / 100
expected_loss = trigger_prob * payout
profit = price - expected_loss - admin_cost
margin = (profit / price) * 100 if price != 0 else 0

# Results
st.subheader("📊 Results")
st.metric(label="Expected Loss ($)", value=f"{expected_loss:.2f}")
st.metric(label="Profit per Sale ($)", value=f"{profit:.2f}")
st.metric(label="Profit Margin (%)", value=f"{margin:.2f}%")

# Profitability Message
if margin >= 50:
    st.success("✅ Target 50% profit margin achieved!")
elif margin > 0:
    st.warning("⚠️ Positive margin, but below 50% target.")
else:
    st.error("❌ Unprofitable at current pricing.")
