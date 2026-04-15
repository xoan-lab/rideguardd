import React, { useMemo, useRef, useState } from 'react';
import { motion, AnimatePresence } from 'framer-motion';
import {
  Bell,
  Bike,
  ChevronRight,
  Clock3,
  Gauge,
  HeartPulse,
  Home,
  MapPin,
  Phone,
  Radio,
  Settings,
  Shield,
  User,
  Users,
  Satellite,
  History,
  Siren,
} from 'lucide-react';

const contactsSeed = [
  { id: 1, name: 'Mom', phone: '+84 123 456 789', status: 'Primary' },
  { id: 2, name: 'Linh', phone: '+84 912 555 222', status: 'Backup' },
  { id: 3, name: 'Bryan', phone: '+84 905 111 444', status: 'Backup' },
];

const activitiesSeed = [
  { id: 1, type: 'Ride started', time: '9:10 AM' },
  { id: 2, type: 'GPS connected', time: '9:11 AM' },
  { id: 3, type: 'Safety check completed', time: '9:12 AM' },
];

function StatPill({ icon: Icon, value, label, tone = 'blue' }) {
  const tones = {
    blue: 'bg-blue-50 text-blue-700',
    green: 'bg-emerald-50 text-emerald-700',
    orange: 'bg-orange-50 text-orange-700',
  };

  return (
    <div className="flex items-center gap-3 rounded-2xl bg-white/90 px-3 py-3 shadow-sm ring-1 ring-black/5">
      <div className={`flex h-10 w-10 items-center justify-center rounded-xl ${tones[tone]}`}>
        <Icon className="h-5 w-5" />
      </div>
      <div>
        <div className="text-[15px] font-bold text-slate-800">{value}</div>
        <div className="text-[11px] text-slate-500">{label}</div>
      </div>
    </div>
  );
}

function QuickAction({ icon: Icon, title, subtitle, color, onClick }) {
  return (
    <button
      onClick={onClick}
      className="flex min-w-[76px] flex-col items-center gap-2 rounded-2xl bg-slate-50 px-3 py-3 text-center transition hover:bg-slate-100"
    >
      <div className={`flex h-10 w-10 items-center justify-center rounded-xl ${color}`}>
        <Icon className="h-5 w-5" />
      </div>
      <div className="text-[12px] font-semibold leading-tight text-slate-700">{title}</div>
      <div className="rounded-full bg-white px-2 py-0.5 text-[10px] text-slate-500 shadow-sm ring-1 ring-slate-200">
        {subtitle}
      </div>
    </button>
  );
}

function BottomNav({ tab, setTab }) {
  const items = [
    { key: 'home', label: 'Home', icon: Home },
    { key: 'activities', label: 'Activities', icon: History },
    { key: 'safety', label: 'Safety', icon: Shield },
    { key: 'profile', label: 'Profile', icon: User },
  ];

  return (
    <div className="mt-4 grid grid-cols-4 border-t border-slate-200 pt-3">
      {items.map((item) => {
        const Icon = item.icon;
        const active = tab === item.key;
        return (
          <button
            key={item.key}
            onClick={() => setTab(item.key)}
            className="flex flex-col items-center gap-1 py-1"
          >
            <Icon className={`h-5 w-5 ${active ? 'text-blue-600' : 'text-slate-400'}`} />
            <span className={`text-[11px] ${active ? 'font-semibold text-blue-600' : 'text-slate-400'}`}>
              {item.label}
            </span>
          </button>
        );
      })}
    </div>
  );
}

function SlideToSend({ onComplete, disabled }) {
  const trackRef = useRef(null);
  const [dragX, setDragX] = useState(0);
  const [done, setDone] = useState(false);

  const maxDrag = 220;

  return (
    <div className="mt-3 rounded-3xl bg-white px-3 py-2 shadow-inner">
      <div ref={trackRef} className="relative h-12 overflow-hidden rounded-full bg-rose-50">
        <div className="pointer-events-none absolute inset-0 flex items-center justify-center text-sm font-semibold text-rose-500">
          {done ? 'SOS Alert Sent' : 'Slide to Send SOS'}
        </div>
        <motion.button
          drag={disabled || done ? false : 'x'}
          dragConstraints={{ left: 0, right: maxDrag }}
          dragElastic={0}
          onDrag={(_, info) => setDragX(Math.max(0, Math.min(maxDrag, info.offset.x)))}
          onDragEnd={(_, info) => {
            const passed = info.offset.x > 170;
            if (passed) {
              setDone(true);
              setDragX(maxDrag);
              onComplete();
            } else {
              setDragX(0);
            }
          }}
          animate={{ x: dragX }}
          className="absolute left-1 top-1 flex h-10 w-10 items-center justify-center rounded-full bg-rose-500 text-white shadow-lg disabled:opacity-50"
          disabled={disabled}
        >
          <Siren className="h-5 w-5" />
        </motion.button>
      </div>
    </div>
  );
}

export default function RideGuardMobileUI() {
  const [tab, setTab] = useState('home');
  const [systemActive, setSystemActive] = useState(true);
  const [gpsConnected, setGpsConnected] = useState(true);
  const [speed, setSpeed] = useState(52);
  const [satellites, setSatellites] = useState(12);
  const [contacts, setContacts] = useState(contactsSeed);
  const [activities, setActivities] = useState(activitiesSeed);
  const [banner, setBanner] = useState('Real-time monitoring is ON');
  const [showSosModal, setShowSosModal] = useState(false);
  const [showManageContacts, setShowManageContacts] = useState(false);
  const [selectedContactId, setSelectedContactId] = useState(1);
  const [showSettings, setShowSettings] = useState(false);
  const [showNotification, setShowNotification] = useState(false);
  const [sosSent, setSosSent] = useState(false);

  const primaryContact = useMemo(
    () => contacts.find((c) => c.id === selectedContactId) || contacts[0],
    [contacts, selectedContactId]
  );

  const sendActivity = (text) => {
    const time = new Date().toLocaleTimeString([], { hour: 'numeric', minute: '2-digit' });
    setActivities((prev) => [{ id: Date.now(), type: text, time }, ...prev.slice(0, 5)]);
  };

  const triggerSos = () => {
    setSosSent(true);
    setShowNotification(true);
    setShowSosModal(false);
    setBanner(`SOS sent to ${primaryContact.name}`);
    sendActivity(`SOS alert sent to ${primaryContact.name}`);
    window.setTimeout(() => setShowNotification(false), 2500);
  };

  const simulateRide = () => {
    const nextSpeed = speed >= 60 ? 18 : speed + 6;
    const nextSatellites = satellites >= 16 ? 9 : satellites + 1;
    setSpeed(nextSpeed);
    setSatellites(nextSatellites);
    setBanner('Ride activity refreshed');
    sendActivity(`Speed updated to ${nextSpeed} km/h`);
  };

  const callContact = () => {
    setBanner(`Calling ${primaryContact.name}...`);
    sendActivity(`Emergency call started to ${primaryContact.name}`);
    setShowNotification(true);
    window.setTimeout(() => setShowNotification(false), 2000);
  };

  const safetyCheck = () => {
    setBanner('Safety check link shared');
    sendActivity('Safety check link sent');
    setShowNotification(true);
    window.setTimeout(() => setShowNotification(false), 2000);
  };

  return (
    <div className="min-h-screen w-full bg-[#f3e0de] p-4 md:p-8">
      <div className="mx-auto flex max-w-5xl items-start justify-center gap-10">
        <div className="relative w-[340px] rounded-[42px] bg-black p-[10px] shadow-2xl">
          <div className="absolute left-1/2 top-2 z-30 h-7 w-36 -translate-x-1/2 rounded-b-3xl bg-black" />
          <div className="relative overflow-hidden rounded-[34px] bg-[#f6f7fb] px-4 pb-4 pt-5">
            <div className="mt-1 flex items-center justify-between">
              <div className="flex items-center gap-2">
                <div className="flex h-9 w-9 items-center justify-center rounded-full bg-blue-100 text-blue-700">
                  <Shield className="h-5 w-5" />
                </div>
                <div>
                  <div className="text-[22px] font-extrabold leading-none text-slate-800">Ride Guard</div>
                  <div className="mt-1 flex items-center gap-2 text-[11px] text-slate-500">
                    <div className="flex items-center gap-1 rounded-full bg-emerald-50 px-2 py-0.5 text-emerald-700">
                      <span className="h-2 w-2 rounded-full bg-emerald-500" />
                      System Active
                    </div>
                    <div className="flex items-center gap-1">
                      <span className="h-2 w-2 rounded-full bg-blue-500" />
                      GPS Connected
                    </div>
                  </div>
                </div>
              </div>
              <button
                onClick={() => setShowSettings(true)}
                className="rounded-full p-2 text-slate-500 transition hover:bg-slate-100"
              >
                <Bell className="h-5 w-5" />
              </button>
            </div>

            <div className="mt-4 overflow-hidden rounded-[24px] bg-white p-3 shadow-sm ring-1 ring-slate-200">
              <div className="relative h-44 overflow-hidden rounded-[20px] bg-gradient-to-br from-blue-100 via-slate-100 to-blue-50">
                <div className="absolute inset-0 opacity-70">
                  <div className="absolute left-5 top-8 h-1 w-52 rotate-[18deg] rounded-full bg-slate-300" />
                  <div className="absolute left-0 top-16 h-1 w-72 -rotate-[8deg] rounded-full bg-slate-300" />
                  <div className="absolute left-10 top-28 h-1 w-60 rotate-[10deg] rounded-full bg-slate-300" />
                  <div className="absolute left-24 top-3 h-32 w-1 rounded-full bg-slate-300" />
                  <div className="absolute right-16 top-0 h-40 w-1 rounded-full bg-slate-300" />
                </div>
                <div className="absolute left-3 top-3 rounded-xl bg-white/90 px-3 py-2 shadow-sm">
                  <div className="text-[14px] font-bold text-blue-700">You&apos;re Protected</div>
                  <div className="text-[10px] text-slate-500">{banner}</div>
                </div>
                <div className="absolute left-1/2 top-1/2 flex -translate-x-1/2 -translate-y-1/2 items-center justify-center">
                  <div className="absolute h-20 w-20 rounded-full bg-blue-400/20 animate-ping" />
                  <div className="absolute h-12 w-12 rounded-full bg-blue-500/30" />
                  <div className="h-5 w-5 rounded-full bg-blue-600 ring-4 ring-white shadow-lg" />
                </div>
                <div className="absolute bottom-3 left-3 right-3 grid grid-cols-2 gap-3">
                  <StatPill icon={Gauge} value={`${speed} km/h`} label="Current Speed" tone="blue" />
                  <StatPill icon={Satellite} value={`${satellites} Satellites`} label="GPS Signal" tone="green" />
                </div>
              </div>
            </div>

            <div className="mt-4 rounded-[24px] bg-gradient-to-r from-red-500 to-orange-500 p-4 text-white shadow-md">
              <div className="flex items-center gap-2 text-[13px] font-bold uppercase tracking-wide">
                <Siren className="h-4 w-4" /> Emergency SOS
              </div>
              <div className="mt-1 text-[12px] text-white/85">Long press to call for help & alert your contacts</div>
              <SlideToSend onComplete={triggerSos} disabled={sosSent} />
            </div>

            <div className="mt-5 flex items-center justify-between">
              <div className="text-[20px] font-extrabold text-slate-800">Quick Actions</div>
              <button
                onClick={() => setTab('activities')}
                className="text-[12px] font-semibold text-blue-600"
              >
                View All
              </button>
            </div>

            <div className="mt-3 flex gap-3 overflow-x-auto pb-1">
              <QuickAction
                icon={Phone}
                title="Call Contacts"
                subtitle="3 People"
                color="bg-blue-100 text-blue-700"
                onClick={callContact}
              />
              <QuickAction
                icon={Shield}
                title="Safety Check"
                subtitle="Share Live"
                color="bg-indigo-100 text-indigo-700"
                onClick={safetyCheck}
              />
              <QuickAction
                icon={Bike}
                title="Ride Record"
                subtitle="Recording"
                color="bg-orange-100 text-orange-700"
                onClick={simulateRide}
              />
              <QuickAction
                icon={Settings}
                title="Settings"
                subtitle="Customize"
                color="bg-emerald-100 text-emerald-700"
                onClick={() => setShowSettings(true)}
              />
            </div>

            <div className="mt-5 rounded-[22px] bg-white p-4 shadow-sm ring-1 ring-slate-200">
              <div className="flex items-center justify-between">
                <div>
                  <div className="flex items-center gap-2 text-[18px] font-extrabold text-slate-800">
                    <Users className="h-5 w-5 text-blue-600" /> My Safe Contacts
                  </div>
                  <div className="text-[12px] text-slate-500">{contacts.length} people will be notified in case of emergency</div>
                </div>
                <button
                  onClick={() => setShowManageContacts(true)}
                  className="rounded-full bg-blue-50 px-3 py-1.5 text-[12px] font-semibold text-blue-700"
                >
                  Manage
                </button>
              </div>
            </div>

            <div className="mt-5 rounded-[22px] bg-white p-4 shadow-sm ring-1 ring-slate-200">
              <div className="flex items-center justify-between">
                <div className="text-[20px] font-extrabold text-slate-800">Today&apos;s Ride</div>
                <button className="text-[12px] font-semibold text-blue-600">View History</button>
              </div>
              <div className="mt-4 grid grid-cols-3 gap-3">
                <div className="rounded-2xl bg-slate-50 p-3 text-center">
                  <MapPin className="mx-auto h-5 w-5 text-blue-600" />
                  <div className="mt-2 text-[18px] font-extrabold text-slate-800">24.8 km</div>
                  <div className="text-[11px] text-slate-500">Distance</div>
                </div>
                <div className="rounded-2xl bg-slate-50 p-3 text-center">
                  <Clock3 className="mx-auto h-5 w-5 text-emerald-600" />
                  <div className="mt-2 text-[18px] font-extrabold text-slate-800">35 min</div>
                  <div className="text-[11px] text-slate-500">Duration</div>
                </div>
                <div className="rounded-2xl bg-slate-50 p-3 text-center">
                  <Gauge className="mx-auto h-5 w-5 text-orange-600" />
                  <div className="mt-2 text-[18px] font-extrabold text-slate-800">42 km/h</div>
                  <div className="text-[11px] text-slate-500">Avg Speed</div>
                </div>
              </div>
            </div>

            <AnimatePresence mode="wait">
              {tab === 'activities' && (
                <motion.div
                  initial={{ opacity: 0, y: 8 }}
                  animate={{ opacity: 1, y: 0 }}
                  exit={{ opacity: 0, y: 8 }}
                  className="mt-5 rounded-[22px] bg-white p-4 shadow-sm ring-1 ring-slate-200"
                >
                  <div className="text-[18px] font-extrabold text-slate-800">Recent Activity</div>
                  <div className="mt-3 space-y-3">
                    {activities.map((item) => (
                      <div key={item.id} className="flex items-center justify-between rounded-2xl bg-slate-50 px-3 py-3">
                        <div className="flex items-center gap-3">
                          <div className="rounded-xl bg-blue-100 p-2 text-blue-700">
                            <Radio className="h-4 w-4" />
                          </div>
                          <div>
                            <div className="text-[13px] font-semibold text-slate-800">{item.type}</div>
                            <div className="text-[11px] text-slate-500">RideGuard event log</div>
                          </div>
                        </div>
                        <div className="text-[11px] text-slate-500">{item.time}</div>
                      </div>
                    ))}
                  </div>
                </motion.div>
              )}
            </AnimatePresence>

            <BottomNav tab={tab} setTab={setTab} />
          </div>
        </div>

        <div className="hidden max-w-md space-y-4 md:block">
          <div className="rounded-3xl bg-white p-6 shadow-xl">
            <div className="text-xl font-extrabold text-slate-800">Interactive functions included</div>
            <div className="mt-3 space-y-2 text-sm text-slate-600">
              <div>• Slide the SOS control to send an emergency alert</div>
              <div>• Tap Call Contacts to simulate emergency calling</div>
              <div>• Tap Safety Check to share a live check link</div>
              <div>• Tap Ride Record to simulate live ride updates</div>
              <div>• Manage contacts to change the primary SOS recipient</div>
              <div>• Open settings to toggle system activity and GPS state</div>
            </div>
          </div>

          <div className="rounded-3xl bg-slate-900 p-6 text-white shadow-xl">
            <div className="text-lg font-bold">Current selected SOS contact</div>
            <div className="mt-3 rounded-2xl bg-white/10 p-4">
              <div className="text-base font-semibold">{primaryContact.name}</div>
              <div className="text-sm text-slate-300">{primaryContact.phone}</div>
              <div className="mt-2 inline-flex rounded-full bg-blue-500/20 px-2 py-1 text-xs text-blue-200">
                {primaryContact.status}
              </div>
            </div>
          </div>
        </div>
      </div>

      <AnimatePresence>
        {showNotification && (
          <motion.div
            initial={{ opacity: 0, y: -20 }}
            animate={{ opacity: 1, y: 0 }}
            exit={{ opacity: 0, y: -20 }}
            className="fixed left-1/2 top-6 z-50 -translate-x-1/2 rounded-2xl bg-slate-900 px-4 py-3 text-sm text-white shadow-2xl"
          >
            {banner}
          </motion.div>
        )}
      </AnimatePresence>

      <AnimatePresence>
        {showManageContacts && (
          <motion.div
            initial={{ opacity: 0 }}
            animate={{ opacity: 1 }}
            exit={{ opacity: 0 }}
            className="fixed inset-0 z-40 flex items-center justify-center bg-black/40 p-4"
          >
            <motion.div
              initial={{ scale: 0.96, opacity: 0 }}
              animate={{ scale: 1, opacity: 1 }}
              exit={{ scale: 0.96, opacity: 0 }}
              className="w-full max-w-sm rounded-3xl bg-white p-5 shadow-2xl"
            >
              <div className="flex items-center justify-between">
                <div className="text-lg font-extrabold text-slate-800">Manage Contacts</div>
                <button onClick={() => setShowManageContacts(false)} className="text-slate-400">Close</button>
              </div>
              <div className="mt-4 space-y-3">
                {contacts.map((contact) => {
                  const active = selectedContactId === contact.id;
                  return (
                    <button
                      key={contact.id}
                      onClick={() => {
                        setSelectedContactId(contact.id);
                        setBanner(`Primary contact set to ${contact.name}`);
                        sendActivity(`Primary contact changed to ${contact.name}`);
                        setShowManageContacts(false);
                        setShowNotification(true);
                        window.setTimeout(() => setShowNotification(false), 2200);
                      }}
                      className={`flex w-full items-center justify-between rounded-2xl px-4 py-3 text-left ring-1 ${
                        active ? 'bg-blue-50 ring-blue-200' : 'bg-slate-50 ring-slate-200'
                      }`}
                    >
                      <div>
                        <div className="font-semibold text-slate-800">{contact.name}</div>
                        <div className="text-sm text-slate-500">{contact.phone}</div>
                      </div>
                      {active && <div className="text-xs font-bold text-blue-600">Selected</div>}
                    </button>
                  );
                })}
              </div>
            </motion.div>
          </motion.div>
        )}
      </AnimatePresence>

      <AnimatePresence>
        {showSettings && (
          <motion.div
            initial={{ opacity: 0 }}
            animate={{ opacity: 1 }}
            exit={{ opacity: 0 }}
            className="fixed inset-0 z-40 flex items-center justify-center bg-black/40 p-4"
          >
            <motion.div
              initial={{ y: 16, opacity: 0 }}
              animate={{ y: 0, opacity: 1 }}
              exit={{ y: 16, opacity: 0 }}
              className="w-full max-w-sm rounded-3xl bg-white p-5 shadow-2xl"
            >
              <div className="flex items-center justify-between">
                <div className="text-lg font-extrabold text-slate-800">Settings</div>
                <button onClick={() => setShowSettings(false)} className="text-slate-400">Close</button>
              </div>
              <div className="mt-5 space-y-4">
                <div className="flex items-center justify-between rounded-2xl bg-slate-50 px-4 py-3">
                  <div>
                    <div className="font-semibold text-slate-800">System Active</div>
                    <div className="text-sm text-slate-500">Enable continuous ride protection</div>
                  </div>
                  <button
                    onClick={() => {
                      setSystemActive((v) => !v);
                      setBanner(systemActive ? 'System paused' : 'System active');
                      sendActivity(systemActive ? 'System deactivated' : 'System activated');
                    }}
                    className={`h-7 w-12 rounded-full p-1 transition ${systemActive ? 'bg-emerald-500' : 'bg-slate-300'}`}
                  >
                    <div className={`h-5 w-5 rounded-full bg-white transition ${systemActive ? 'translate-x-5' : ''}`} />
                  </button>
                </div>
                <div className="flex items-center justify-between rounded-2xl bg-slate-50 px-4 py-3">
                  <div>
                    <div className="font-semibold text-slate-800">GPS Connected</div>
                    <div className="text-sm text-slate-500">Use live location and speed</div>
                  </div>
                  <button
                    onClick={() => {
                      setGpsConnected((v) => !v);
                      setBanner(gpsConnected ? 'GPS disconnected' : 'GPS connected');
                      sendActivity(gpsConnected ? 'GPS disconnected' : 'GPS connected');
                    }}
                    className={`h-7 w-12 rounded-full p-1 transition ${gpsConnected ? 'bg-blue-500' : 'bg-slate-300'}`}
                  >
                    <div className={`h-5 w-5 rounded-full bg-white transition ${gpsConnected ? 'translate-x-5' : ''}`} />
                  </button>
                </div>
                <button
                  onClick={() => {
                    setShowSettings(false);
                    setShowSosModal(true);
                  }}
                  className="flex w-full items-center justify-between rounded-2xl bg-rose-50 px-4 py-3 text-rose-600"
                >
                  <span className="font-semibold">Open Emergency Actions</span>
                  <ChevronRight className="h-4 w-4" />
                </button>
              </div>
            </motion.div>
          </motion.div>
        )}
      </AnimatePresence>

      <AnimatePresence>
        {showSosModal && (
          <motion.div
            initial={{ opacity: 0 }}
            animate={{ opacity: 1 }}
            exit={{ opacity: 0 }}
            className="fixed inset-0 z-40 flex items-end justify-center bg-black/40 p-4 md:items-center"
          >
            <motion.div
              initial={{ y: 20, opacity: 0 }}
              animate={{ y: 0, opacity: 1 }}
              exit={{ y: 20, opacity: 0 }}
              className="w-full max-w-sm rounded-3xl bg-white p-5 shadow-2xl"
            >
              <div className="flex items-center gap-3">
                <div className="rounded-2xl bg-rose-100 p-3 text-rose-600">
                  <HeartPulse className="h-6 w-6" />
                </div>
                <div>
                  <div className="text-lg font-extrabold text-slate-800">Emergency Actions</div>
                  <div className="text-sm text-slate-500">Choose the fastest response</div>
                </div>
              </div>
              <div className="mt-4 space-y-3">
                <button
                  onClick={callContact}
                  className="flex w-full items-center justify-between rounded-2xl bg-blue-50 px-4 py-3 text-blue-700"
                >
                  <span className="font-semibold">Call {primaryContact.name}</span>
                  <Phone className="h-4 w-4" />
                </button>
                <button
                  onClick={triggerSos}
                  className="flex w-full items-center justify-between rounded-2xl bg-rose-50 px-4 py-3 text-rose-600"
                >
                  <span className="font-semibold">Send SOS Alert</span>
                  <Siren className="h-4 w-4" />
                </button>
                <button
                  onClick={() => setShowSosModal(false)}
                  className="w-full rounded-2xl bg-slate-100 px-4 py-3 font-semibold text-slate-600"
                >
                  Cancel
                </button>
              </div>
            </motion.div>
          </motion.div>
        )}
      </AnimatePresence>
    </div>
  );
}
